# jar, war, 배포방법

## jar

- Jar 파일은 Java Archive의 약자로, Java 클래스, 메타데이터, 리소스 파일 등을 하나의 파일로 묶어서 배포하는 방법이다. 주로 Java 애플리케이션에서 사용되며, Java 클래스 파일과 라이브러리 파일들을 압축해서 하나의 Jar 파일로 만든다.
- Jar 파일은 Java의 실행환경을 갖춘 JVM(Java Virtual Machine) 상에서 실행된다. 또한, 특정 운영체제에 종속되지 않기 때문에 이식성이 높아 많은 플랫폼에서 사용된다.

## war

- War 파일은 Web Archive의 약자로, Java 웹 애플리케이션을 하나의 파일로 묶어 배포하는 방법이다. Java 웹 애플리케이션은 일반적으로 여러 개의 Java 파일과 웹 자원 파일(HTML, CSS, JavaScript, 이미지 파일 등)이 함께 사용되기 때문에 이를 하나의 파일로 묶는 것이 유리하다.
- War 파일은 Java EE(Enterprise Edition) 애플리케이션 서버에서 동작한다. 이 파일 형식은 Java 웹 애플리케이션의 배포를 표준화하기 위해 만들어졌으며, Web Container라는 특정한 서버에서 실행된다.

## 배포방법

- ### jar
  - Jar 파일은 Java의 실행환경을 갖춘 JVM 상에서 실행된다. 따라서, Jar 파일을 실행하려면 JDK(Java Development Kit)가 설치되어 있어야 한다. Jar 파일을 실행하려면 다음과 같은 명령어를 사용한다.
  ```bash
    java -jar [jar파일명].jar
  ```
- ### war

  - War 파일은 Java EE 애플리케이션 서버에서 실행된다. Java EE 애플리케이션 서버에는 Tomcat, JBoss, WebLogic, WebSphere 등이 있다.
  - 웹 애플리케이션을 빌드하고 War 파일을 생성하려면 다음과 같은 명령어를 사용한다.

  ```bash
    jar -cvf [war파일명].war [빌드할 디렉토리/파일명]
  ```

  - 프로젝트를 빌드
  - WAR 파일 생성 확인(build/libs/server-0.0.1-SNAPSHOT.war)
  - WAR 파일의 압축을 풀어서 내용물을 확인
  - WAR 파일을 톰캣 서버에 배포

    1. 톰캣 서버를 종료
    2. 톰캣폴더/webapps 하위를 모두 삭제
    3. 빌드된 server-0.0.1-SNAPSHOT.war 파일을 복사
    4. 톰캣폴더/webapps 하위에 붙여넣기
    5. 이름을 변경 (ROOT.war)
    6. 톰캣 서버를 실행
    7. 실행 결과를 확인 (http://localhost:8080/index.html, http://localhost:8080/test)

  - WAR 파일은 웹 애플리케이션 서버(WAS)에 배포할 때 사용하는 파일이며, JAR 파일과 달리 웹 애플리케이션 서버 위에서 실행된다. WAR 파일은 HTML, CSS 등의 정적 리소스와 클래스 파일을 모두 포함하며, WEB-INF 폴더 하위에는 자바 클래스와 라이브러리, 그리고 설정 정보가 들어가는 곳이다. WAR 파일을 톰캣에 배포하기 위해서는 WAR 파일을 톰캣 폴더의 webapps 폴더 하위에 복사하고 이름을 ROOT.war로 변경한 후 톰캣을 실행하면 된다.

## war 배포의 단점
