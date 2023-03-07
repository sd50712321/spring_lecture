1. 자바란 무엇인가요?
   - 자바(Java)는 객체지향 프로그래밍 언어로, 1995년 썬 마이크로시스템즈(Sun Microsystems)에서 개발하였습니다. 현재는 오라클(Oracle)이 관리하고 있습니다.
   - 자바는 플랫폼에 독립적인 특징을 가지고 있으며, 가상머신을 사용해 어떤 운영체제에서든 실행될 수 있습니다.
2. 자바의 특징은 무엇인가요?
   - 플랫폼에 독립적입니다. 즉, 어떤 운영체제에서든 실행될 수 있습니다.
   - 객체지향 언어입니다.
   - 가비지 컬렉션(Garbage Collection)을 통해 자동으로 메모리 관리가 이루어집니다.
   - 멀티스레드를 지원합니다.
   - 안정성이 높고 보안성이 좋습니다.
3. 객체 지향 프로그래밍(OOP)이란 무엇인가요?
   - 객체 지향 프로그래밍(Object-Oriented Programming)은 프로그램을 여러 개의 객체로 분할하고, 객체들 간의 상호작용을 통해 프로그램을 구성하는 프로그래밍 패러다임이다.
   - 객체란 속성과 행위를 가지고 있는 하나의 독립된 단위를 말한다.
   - 객체는 클래스(Class)라는 틀을 기반으로 생성되며, 클래스는 객체를 생성하기 위한 일종의 설계도 역할을 한다.
   - 객체 지향 프로그래밍의 주요 특징으로는 캡슐화(Encapsulation), 상속(Inheritance), 다형성(Polymorphism)이 있다.
4. 자바에서 클래스(class)란 무엇인가요?
   - 자바에서 클래스(Class)는 객체를 생성하기 위한 일종의 설계도 역할을 한다.
   - 클래스는 속성과 행위를 포함하며, 객체를 생성하기 위한 데이터와 메서드를 정의한다.
   - 객체 지향 프로그래밍에서 클래스는 캡슐화(Encapsulation)의 개념을 구현하는 데 중요한 역할을 한다.
5. 객체(Object)란 무엇인가요?
   - 객체(Object)는 클래스(Class)를 기반으로 생성된 하나의 독립된 단위를 말한다.
6. 생성자(Constructor)란 무엇인가요?
   - 생성자는 인스턴스를 생성할 때 호출되는 특별한 메서드입니다.
   - 클래스 이름과 동일한 이름을 가지며 반환값이 없습니다.
   - 인스턴스를 초기화하는 역할을 합니다.
   - 인스턴스 생성시 호출되기 때문에, 생성자는 클래스의 필드값을 초기화하거나, 인스턴스 변수를 초기화하는 등의 작업을 수행할 수 있습니다.
7. 인스턴스(Instance)란 무엇인가요?
   - 클래스에서 생성된 객체를 말합니다.
   - new 키워드를 사용하여 클래스를 인스턴스화하면, 힙(heap) 메모리 영역에 객체가 생성됩니다.
   - 생성된 인스턴스는 해당 클래스의 멤버 변수와 메서드를 사용할 수 있습니다.
8. 상속(Inheritance)이란 무엇인가요?
   - 상속은 객체 지향 프로그래밍에서 클래스들 사이에 부모-자식 관계를 설정하는 것입니다.
   - 자식 클래스는 부모 클래스의 멤버 변수와 메서드를 물려받을 수 있습니다.
   - 상속을 통해 코드 중복을 줄이고, 유지보수를 용이하게 할 수 있습니다.
9. 오버라이딩(Overriding)이란 무엇인가요?
   - 오버라이딩은 상속 관계에서 부모 클래스의 메서드를 자식 클래스에서 재정의하는 것입니다.
   - 자식 클래스에서 부모 클래스의 메서드를 동일한 이름으로 다시 구현하면, 자식 클래스의 메서드가 실행됩니다.
   - 오버라이딩을 통해 자식 클래스는 부모 클래스의 기능을 덮어쓰거나, 확장할 수 있습니다.
10. 다형성(Polymorphism)이란 무엇인가요?
    - 다형성은 하나의 변수나 메서드가 여러 타입에 속할 수 있는 것을 의미합니다.
    - 부모 클래스 타입의 변수에 자식 클래스의 인스턴스를 대입하면, 부모 클래스의 메서드를 호출하더라도 자식 클래스의 오버라이딩된 메서드가 실행됩니다.
    - 다형성을 통해 코드의 재사용성과 유지보수성을 향상시킬 수 있습니다.
11. 추상 클래스(Abstract Class)
    - 추상 클래스는 일반 클래스와 달리 객체를 생성할 수 없으며, 자식 클래스에서 상속받아 구현해야만 사용할 수 있는 클래스입니다. 일반 클래스와 마찬가지로 필드, 생성자, 메소드를 가질 수 있습니다. 추상 클래스는 abstract 키워드를 사용하여 정의하며, 추상 메소드 또는 일반 메소드를 포함할 수 있습니다. 추상 클래스는 객체 지향 프로그래밍의 다형성(Polymorphism)을 구현하는 데 사용됩니다.
12. 인터페이스(Interface)
    - 인터페이스는 추상 클래스와 마찬가지로 객체를 생성할 수 없으며, 자식 클래스에서 상속받아 구현해야만 사용할 수 있는 클래스입니다. 추상 클래스와 달리 인터페이스는 상수와 추상 메소드만을 가질 수 있습니다. 인터페이스는 클래스 간의 결합도를 낮추고, 다형성을 구현하는 데 사용됩니다.
13. 예외(Exception)
    - 예외란 실행 중 발생한 오류나 예기치 않은 상황을 말합니다. 자바에서는 예외를 처리하기 위해 Exception 클래스와 그 하위 클래스들을 제공합니다. Exception 클래스는 모든 예외의 부모 클래스이며, RuntimeException 클래스를 상속한 RuntimeException과 그 하위 클래스는 예외 처리가 강제되지 않습니다.
14. try-catch-finally 블록
    - try-catch-finally 블록은 예외 처리를 위한 문법입니다. try 블록에서 예외가 발생하면, 해당 예외 타입에 맞는 catch 블록으로 제어가 이동합니다. finally 블록은 예외 발생 여부에 상관없이 반드시 실행됩니다.
15. 자바의 예외 처리 방법
    - 자바에서는 예외를 처리하기 위해 try-catch-finally 블록을 사용합니다. 예외가 발생할 가능성이 있는 코드를 try 블록에 넣고, 예외가 발생했을 때 처리할 코드를 catch 블록에 넣습니다. finally 블록은 선택적으로 사용할 수 있으며, 예외 발생 여부와 상관없이 항상 실행됩니다. 예외 처리를 통해 예외 상황에 대처하고, 프로그램의 안정성을 높일 수 있습니다.
16. 자바에서 제공하는 자료형(primitive data type)은 무엇인가요?
    - boolean : true 또는 false 값을 가지는 논리 자료형
    - byte : -128부터 127까지의 8비트 부호 있는 정수 자료형
    - short : -32,768부터 32,767까지의 16비트 부호 있는 정수 자료형
    - int : -2,147,483,648부터 2,147,483,647까지의 32비트 부호 있는 정수 자료형
    - long : -9,223,372,036,854,775,808부터 9,223,372,036,854,775,807까지의 64비트 부호 있는 정수 자료형
    - float : 1.4e-45f 부터 3.4e+38f까지의 32비트 단정도 부동소수점 자료형
    - double : 4.9e-324 부터 1.8e+308까지의 64비트 배정도 부동소수점 자료형
    - char : 0부터 65,535까지의 16비트 유니코드 문자 자료형
17. Wrapper 클래스(Wrapper Class)란 무엇인가요?
    - Wrapper 클래스(Wrapper Class)는 기본 자료형(primitive data type)을 객체로 다룰 수 있도록 만든 클래스입니다. 이를 사용하여 기본 자료형과 관련된 메서드를 사용할 수 있습니다.
18. String 클래스란 무엇인가요?
    - String 클래스는 문자열을 다루는 클래스입니다. 문자열을 다루는 다양한 메서드를 제공하며, 불변(immutable)의 특징을 가집니다.
19. StringBuffer와 StringBuilder의 차이점은 무엇인가요?
    - StringBuffer와 StringBuilder는 String과 같이 문자열을 다루는 클래스입니다. 하지만 String과는 달리 가변(mutable)의 특징을 가집니다. 둘 다 문자열을 처리하는데 유용하며, 차이점은 스레드 안전(thread-safe)의 유무입니다. StringBuffer는 스레드 안전(thread-safe)하므로 멀티스레드 환경에서 안전하게 사용할 수 있으며, StringBuilder는 스레드 안전하지 않습니다.
20. 스레드 안전(thread-safe)이란?
    - 멀티 스레드 환경에서 여러 스레드가 동시에 공유하는 자원(변수, 객체 등)에 대해 동시 접근이 발생하더라도 의도한 대로 동작하는 것을 말합니다.
    - 스레드 안전성을 보장하지 않으면, 예상치 못한 결과가 발생할 수 있습니다. 여러 스레드에서 동시에 한 변수를 수정하는 경우, 각 스레드에서 변경한 값을 서로 덮어쓰는 문제가 발생할 수 있습니다. 이렇게 되면 프로그램의 실행 결과가 예상과 다를 수 있습니다.
    - 따라서 멀티 스레드 환경에서 안전하게 공유 자원을 사용하려면 스레드 간 동기화(synchronization)를 해주어야 합니다. 스레드 간 동기화를 통해 여러 스레드가 공유하는 자원에 대한 접근을 제어하고, 한 스레드가 사용 중인 자원에 다른 스레드가 접근하지 못하도록 보호합니다.
21. 제네릭(Generic)이란 무엇인가요?
    - 제네릭(Generic)은 자바에서 컬렉션(Collection)을 사용할 때, 타입 안정성(type safety)을 보장하기 위해 사용하는 개념입니다. 제네릭을 사용하면 컬렉션에 저장하는 요소의 자료형을 미리 지정할 수 있으며, 이를 통해 컴파일 시점에 타입 에러를 체크할 수 있습니다.
22. 컬렉션(Collection)이란 무엇인가요?
    - 컬렉션(Collection)은 객체를 모아놓은 자료 구조를 의미합니다. 자바에서는 컬렉션을 다루기 위해 java.util 패키지에서 여러 가지 클래스와 인터페이스를 제공합니다.
23. List와 Set의 차이점은 무엇인가요?
    - List는 순서가 있는 데이터의 집합으로, 데이터의 중복을 허용합니다. Set은 순서가 없는 데이터의 집합으로, 데이터의 중복을 허용하지 않습니다.
24. Map이란 무엇인가요?
    - Map은 key-value 쌍으로 이루어진 데이터의 집합입니다. key는 중복될 수 없으며, value는 중복될 수 있습니다.
25. Iterator와 ListIterator의 차이점은 무엇인가요?
    - Iterator와 ListIterator는 컬렉션의 원소를 순회하는 데 사용되는 인터페이스입니다. Iterator는 단방향 순회만 가능하며, ListIterator는 양방향 순회가 가능합니다.
26. 자바에서 사용하는 연산자(operator)의 종류는 무엇이 있나요?
    - 자바에서 사용하는 연산자의 종류에는 산술 연산자, 비교 연산자, 논리 연산자, 비트 연산자, 쉬프트 연산자 등이 있습니다.
27. 제어문(Control Statement)이란 무엇인가요?
    - 제어문은 프로그램의 실행 흐름을 제어하는 데 사용되는 구문으로, 조건문과 반복문이 대표적입니다.
28. 반복문(Loop)에는 어떤 종류가 있나요?
    - 반복문에는 for문, while문, do-while문이 있습니다.
29. 배열(Array)이란 무엇인가요?
    - 배열은 동일한 자료형의 데이터를 순차적으로 나열한 자료구조입니다. 인덱스(index)를 통해 배열의 요소(element)에 접근할 수 있으며, 배열은 고정된 크기를 가지기 때문에 크기를 변경할 수 없습니다.
30. 메소드(Method)란 무엇인가요?
    - 메소드는 하나의 기능을 수행하는 코드의 집합입니다. 클래스 내부에 정의되며, 객체를 생성하지 않고도 호출할 수 있습니다.
31. 패키지(Package)란 무엇인가요?
    - 패키지는 클래스, 인터페이스, 그리고 다른 패키지들을 담는 논리적인 단위입니다. 클래스 이름이 같아도 패키지가 다르면 다른 클래스로 인식합니다. 패키지는 클래스를 조직화하고 관리하기 위해 사용됩니다.
32. 자바에서 열거형(Enum)이란 무엇인가요? 그리고 어떻게 사용하나요?
    - 열거형은 상수의 집합을 나타내는 자료형입니다.
    - enum 키워드를 사용하여 선언하며, 여러 개의 상수 값을 콤마로 구분하여 나열합니다.
    - 열거형은 상수와 함께 메소드, 생성자 등을 가질 수 있습니다.
    - 열거형을 사용하면 코드 가독성과 안정성을 높일 수 있습니다.
33. 자바에서 제공하는 어노테이션(Annotation)이란 무엇인가요? 그리고 어떻게 사용하나요?
    - 어노테이션은 소스 코드에 메타데이터를 추가하여 컴파일러나 런타임에 사용할 수 있는 정보를 제공합니다.
    - @ 기호를 사용하여 표시하며, 선언된 대상에 따라 타입, 필드, 메소드, 생성자, 매개변수 등에 적용할 수 있습니다.
    - 어노테이션은 컴파일러가 경고를 표시하거나 코드를 생성하는 데 사용될 수 있습니다.
34. 자바에서 제공하는 람다식(Lambda Expression)이란 무엇인가요? 그리고 어떻게 사용하나요?
    - 람다식은 함수형 프로그래밍에서 사용되며, 메소드를 하나의 식으로 표현한 것입니다.
    - 람다식은 매개변수와 반환값을 갖는 메소드를 표현하는데 사용됩니다.
    - -> 기호를 사용하여 매개변수와 메소드 식을 연결합니다.
      람다식은 함수형 인터페이스를 구현한 객체를 생성하는 용도로 사용됩니다.
35. 자바에서 제공하는 스트림(Stream)이란 무엇인가요? 그리고 어떻게 사용하나요?
    - 스트림은 자바 8에서 추가된 기능으로, 컬렉션과 배열을 함수형으로 처리할 수 있도록 지원합니다.
    - 스트림은 데이터 소스를 추상화하여 다양한 데이터 소스를 같은 방식으로 다룰 수 있습니다.
    - 중간 연산과 최종 연산으로 구성되며, 중간 연산은 필터링이나 매핑과 같은 작업을 수행하고 최종 연산은 스트림의 결과를 반환합니다.
    - 스트림은 병렬 처리를 지원하여 대용량 데이터를 빠르게 처리할 수 있습니다.