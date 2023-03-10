## Garbage collection?

- Garbage Collector는 자바에서 메모리를 관리하는 기능 중 하나로, 더 이상 사용하지 않는 객체를 찾아 메모리에서 자동으로 해제해주는 역할을 합니다.

- Java에서는 개발자가 명시적으로 메모리를 할당하거나 해제하는 것이 아니라, JVM에서 Garbage Collector가 자동으로 수행합니다. 이를 통해 메모리 관리의 번거로움을 줄이고, 개발자가 더욱 안정적인 프로그램을 작성할 수 있도록 도와줍니다.

- Garbage Collector의 작동 원리는 크게 두 가지로 나뉩니다.

- Mark and Sweep Algorithm
  메모리 상에서 더 이상 사용되지 않는 객체를 찾기 위해 모든 객체를 순회하면서 사용 여부를 표시하는 Mark 단계와, 사용되지 않는 객체를 메모리에서 해제하는 Sweep 단계로 나뉩니다. Mark 단계에서는 루트(root) 객체부터 시작하여 연결된 객체를 모두 순회하면서 사용 여부를 표시합니다. Sweep 단계에서는 Mark 단계에서 사용 여부를 표시하지 않은 객체들을 해제합니다.

- Copying Algorithm
  메모리를 두 개의 영역으로 나누고, 한 영역에 객체를 할당하면서 사용 가능한 메모리 공간을 계속해서 추적합니다. 메모리 공간이 부족해지면, 사용 중인 객체를 다른 영역으로 복사하고, 사용 중이지 않은 영역의 객체를 해제합니다. 이를 통해 메모리 사용률을 최적화하고, 할당 시간을 줄이는 효과를 얻을 수 있습니다.

- Garbage Collector의 성능은 다양한 요소에 따라 영향을 받습니다. 가장 큰 영향을 미치는 요소는 JVM의 버전과 Garbage Collector의 종류입니다. 일반적으로 최신 버전의 JVM과 G1(Garbage First) Collector를 사용하는 것이 가장 좋은 성능을 보입니다. 또한, Garbage Collector의 동작을 최적화하려면 코드에서 사용하는 객체의 생성 및 소멸 시점을 잘 파악하여 최소화해야 합니다. 이를 통해 Garbage Collector의 작업량을 줄이고, 애플리케이션의 성능을 개선할 수 있습니다.
