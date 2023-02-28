# jar, war, 배포방법

## jar

- Jar 파일은 Java Archive의 약자로, Java 클래스, 메타데이터, 리소스 파일 등을 하나의 파일로 묶어서 배포하는 방법입니다. 주로 Java 애플리케이션에서 사용되며, Java 클래스 파일과 라이브러리 파일들을 압축해서 하나의 Jar 파일로 만듭니다.
  Jar 파일은 Java의 실행환경을 갖춘 JVM(Java Virtual Machine) 상에서 실행됩니다. 또한, 특정 운영체제에 종속되지 않기 때문에 이식성이 높아 많은 플랫폼에서 사용됩니다.

## war

- War 파일은 Web Archive의 약자로, Java 웹 애플리케이션을 하나의 파일로 묶어 배포하는 방법입니다. Java 웹 애플리케이션은 일반적으로 여러 개의 Java 파일과 웹 자원 파일(HTML, CSS, JavaScript, 이미지 파일 등)이 함께 사용되기 때문에 이를 하나의 파일로 묶는 것이 유리합니다.
  War 파일은 Java EE(Enterprise Edition) 애플리케이션 서버에서 동작합니다. 이 파일 형식은 Java 웹 애플리케이션의 배포를 표준화하기 위해 만들어졌으며, Web Container라는 특정한 서버에서 실행됩니다.

## 배포방법

- ### jar
  - Jar 파일은 Java의 실행환경을 갖춘 JVM 상에서 실행됩니다. 따라서, Jar 파일을 실행하려면 JDK(Java Development Kit)가 설치되어 있어야 합니다. Jar 파일을 실행하려면 다음과 같은 명령어를 사용합니다.
  ```bash
    java -jar [jar파일명].jar
  ```
- ### war
  - War 파일은 Java EE 애플리케이션 서버에서 실행됩니다. Java EE 애플리케이션 서버에는 Tomcat, JBoss, WebLogic, WebSphere 등이 있습니다.
    웹 애플리케이션을 빌드하고 War 파일을 생성하려면 다음과 같은 명령어를 사용합니다.
  ```bash
    jar -cvf [war파일명].war [빌드할 디렉토리/파일명]
  ```
