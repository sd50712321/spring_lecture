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
- 이런 것들을 전부 간편하게 요청받거나 응답할 수 있도록 도와주는 것이 서블릿이다
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

### HttpServletRequest

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
