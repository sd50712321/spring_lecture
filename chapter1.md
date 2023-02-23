# 서블릿

## 서블릿의 역할?

- 보통 http 통신을 할 때 서버에서는 요청한 사람의 http 헤더 및 본문을 해석한다
- 아래는 http 요청시 서버에 보내는 요청 메시지 전문
  ```text
  POST /save HTTP/1.1
  Host: localhost:8080
  Content-Type: application/x-www-form-urlencoded
  username=test
  ```
- 전부 텍스트로 되어 있기 때문에 만약 각 항목별로 원하는 내용을 파악하려면 엄청나게 복잡한 텍스트의 파싱을 서버가 직접 해야한다.
- 이런 것들을 전부 간편하게 요청받거나 응답할 수 있도록 도와주는 것이 서블릿이다.
- 스프링부트에는 톰캣(was) 내장되어 있었지만 그 이전에는 톰캣을 직접 설치하고 서블릿 코드를 클래스 파일로 빌드, 톰캣서버를 실행했었다. 이제는 톰캣 설치 없이 바로 서블릿 코드를 실행할 수 있다

#### main.servlet.ServletApplication

```java
//
@ServletComponentScan //서블릿 자동 등록 @SpringBootApplication
public class ServletApplication {
      public static void main(String[] args) {
          SpringApplication.run(ServletApplication.class, args);
```

#### main.servlet.test.TestServlet

```java
@WebServlet(name = "testServlet", urlPatterns = "/test")
  public class TestServlet extends HttpServlet {
@Override
      protected void service(HttpServletRequest request, HttpServletResponse
  response)
              throws ServletException, IOException {
          System.out.println("TestServlet.service");
          System.out.println("request = " + request);
          System.out.println("response = " + response);
          String username = request.getParameter("username");
          System.out.println("username = " + username);
          response.setContentType("text/plain");
          response.setCharacterEncoding("utf-8");
          response.getWriter().write("test " + username);
}
```

- 서블릿은 이런 요청 및 응답을 하나의 서블릿 컨테이너로 만들어서 관리한다 서블릿 컨테이너는 다음과 같은 HttpServletRequest, HttpServletResponse 객체를 반환하는데 요청 및 응답에 관한 정보를 쉽게 확인할 수 있도록 도와준다

## 서블릿 컨테이너란?

- 서블릿의 생명주기를 관리한다
- 서블릿의 인스턴스는 처음 요청이 들어왔을 때 생성되며, 서블릿 컨테이너에서는 여러 요청을 처리할 수 있는 서블릿 인스턴스 풀을 관리한다.
- 서블릿이 더 이상 사용되지 않을 때는 서블릿 컨테이너에서 해당 서블릿 인스턴스를 제거한다.

## Servlet 생명 주기

- 서블릿은 서버가 시작될 때 인스턴스화되며, 클라이언트의 요청이 들어올 때마다 해당 서블릿의 service() 메서드가 호출된다.
- 따라서 서블릿은 매 요청마다 인스턴스가 생성되는 것이 아니라, 서버가 시작될 때 인스턴스가 생성되고, 이후 요청이 들어올 때마다 이미 생성된 인스턴스의 service() 메서드가 호출된다.
- 서블릿의 생명 주기를 이해하면, 서블릿에서 필요한 초기화 작업이나 정리 작업을 적절히 수행할 수 있다.

- 서블릿의 생명 주기는 다음과 같습니다.

  - 서블릿 인스턴스 생성
  - init() 메서드 호출
  - service() 메서드 호출
  - destroy() 메서드 호출
  - 서블릿 인스턴스 소멸

- init() 메서드는 서블릿 인스턴스가 생성된 직후에 호출되며, 서블릿 초기화 작업을 수행하는 데 사용된다.
- service() 메서드는 클라이언트의 요청이 들어올 때마다 호출되며, 실제로 클라이언트의 요청을 처리하는 로직이 들어가게 된다.
- destroy() 메서드는 서블릿 인스턴스가 소멸되기 전에 호출되며, 서블릿 정리 작업을 수행하는 데 사용된다.

## HttpServletRequest

- 클라이언트가 보내온 요청 메시지를 돕는 메서드 들이 들어있다.
  - request.getMethod(): 요청 메서드
  - request.getProtocol(): 요청 프로토콜
  - request.getSchema(): 요청 스키마
  - request.getRequestURL(): 요청 URL
  - request.getRequestURI(): 요청 URI
  - request.getQueryString(): 요청 쿼리
  ```text
  request.getMethod() = GET
  request.getProtocol() = HTTP/1.1
  request.getScheme() = http
  request.getRequestURL() = http://localhost:8080/request-header
  request.getRequestURI() = /request-header
  request.getQueryString() = username=hello
  ```
- 각종 요청 정보를 확인할 수 있다
- header는 다음과 같이 확인할 수 있다

```java
private void printHeaders(HttpServletRequest request) {
      System.out.println("--- Headers - start ---");
      Enumeration<String> headerNames = request.getHeaderNames();
      while (headerNames.hasMoreElements()) {
          String headerName = headerNames.nextElement();
          System.out.println(headerName + ": " + request.getHeader(headerName));
      }
}
```

```text
host: localhost:8080
  connection: keep-alive
  cache-control: max-age=0
  sec-ch-ua: "Chromium";v="88", "Google Chrome";v="88", ";Not A Brand";v="99"
  sec-ch-ua-mobile: ?0
  upgrade-insecure-requests: 1
  user-agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 11_2_0) AppleWebKit/537.36
  (KHTML, like Gecko) Chrome/88.0.4324.150 Safari/537.36
  accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/
  webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
  sec-fetch-site: none
  sec-fetch-mode: navigate
  sec-fetch-user: ?1
  sec-fetch-dest: document
  accept-encoding: gzip, deflate, br
  accept-language: ko,en-US;q=0.9,en;q=0.8,ko-KR;q=0.7
```

- 만약 클라이언트가 쿼리 파라미터로 데이터를 전송한다면?

```Java
@WebServlet(name = "testParamServlet", urlPatterns = "/request-param")
  public class TestParamServlet extends HttpServlet {
@Override
      protected void service(HttpServletRequest request, HttpServletResponse
  resp) throws ServletException, IOException {
System.out.println("[전체 파라미터 조회] - start");
          request.getParameterNames().asIterator()
                  .forEachRemaining(paramName -> System.out.println(paramName +
"=" + request.getParameter(paramName))); System.out.println("[전체 파라미터 조회] - end");
          System.out.println();
System.out.println("[단일 파라미터 조회]");
String username = request.getParameter("username"); System.out.println("request.getParameter(username) = " + username);
          String age = request.getParameter("age");
          System.out.println("request.getParameter(age) = " + age);
          System.out.println();
System.out.println("[이름이 같은 복수 파라미터 조회]");
// 같은 파라미터로 중복해서 들어오면 배열로 다 받을 수 있음
System.out.println("request.getParameterValues(username)"); String[] usernames = request.getParameterValues("username"); for (String name : usernames) {
              System.out.println("username=" + name);
          }
          resp.getWriter().write("ok");
      }
}
```

## HttpServletResponse

- HttpServletResponse
  HttpServletResponse 객체는 HTTP 응답 메시지를 돕는 메서드들이 들어있다.
- response.getWriter() 메서드를 호출하면, HTTP 응답 바디를 출력할 수 있는 PrintWriter 객체를 얻을 수 있다.
- PrintWriter 객체를 이용하여, 클라이언트에게 전송할 HTTP 응답 바디를 생성할 수 있다.
- response.setContentType("text/html")과 같은 메서드를 이용하여, HTTP 응답 헤더의 Content-Type 값을 설정할 수도 있다.
