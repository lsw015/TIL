# Object Oriented Programming

객체 지향 프로그래밍이란 프로그래밍에서 필요한 데이터를 추상화시켜 상태와 행위를 가진 객체를 만들고 그 객체들 간의 유기적인 상호작용을 통해 로직을 구성하는 프로그래밍 방법이다.

## 클래스

- 추상화를 거쳐 데이터의 속성(attribute)과 행위(behavior)를 변수와 메서드로 정의한 것

## 객체 지향 프로그래밍의 장단점

### 장점

#### 코드 재사용이 용이

- 이미 작성된 코드를 가져와서 사용할 수 있고 상속을 통해 확장해서 사용할 수 있음.

#### 유지보수가 쉬움

- 수정해야 할 부분이 클래스 내부에 변수혹은 메소드로 있기 때문에 해당 부분만 수정하면 됨.

### 단점

#### overhead가 많이 발생함

- 객체 간의 정보 교환이 모두 메시지 교환을 통해 일어나므로 실행 시스템에 많은 overhead가 발생하게 된다

#### 객체가 상태를 갖고있음

- 객체내에 변수가 존재하여 동일한 입력에도 변수 값에 따라 다른 값을 반환할 수도 있다.(side effect가 있음)
- 이 변수때문에 객체가 예측할 수 없는 상태를 갖게 되어 애플리케이션 내부에서 버그를 발생시키고 테스팅을 하기 어렵게만든다.
- 이러한 이유로 함수형 프로그래밍 패러다임이 최근 주목받고 있다.

## 객체 지향적 설계 원칙(SOLID원칙)

### SRP(Single Responsibility Principle): 단일 책임 원칙

- 클래스는 단 하나의 책임을 가져야 하며 클래스를 변경하는 이유는 단 하나의 이유이어야 한다.

### OCP(Open-Closed Principle): 개방-폐쇄 원칙

- 확장에는 열려 있어야 하고 변경에는 닫혀 있어야 한다.
- 자신을 확장시키는 것에는 열려있고, 주변의 변화에 대해서는 닫혀있어야한다.

### LSP(Liskov Substitution Principle): 리스코프 치환 원칙

- 상위 타입의 객체를 하위 타입의 객체로 치환해도 상위 타입을 사용하는 프로그램은 정상적으로 동작해야 한다.

### ISP(Interface Segregation Principle): 인터페이스 분리 원칙

- 인터페이스는 그 인터페이스를 사용하는 클라이언트를 기준으로 분리해야 한다.
- 한 클래스는 자신이 사용하지 않는 인터페이스는 구현하지 말아야한다.

### DIP(Dependency Inversion Principle): 의존 역전 원칙

- 고수준 모듈은 저수준 모듈의 구현에 의존해서는 안된다.

## OOP의 특징

### 추상화

- 객체들에서 공통의 속성이나 기능을 묶어 상위 클래스를 생성하는것(뱀, 오리, 닭 이라는 객체들이 있을때 이들을 동물 또는 생물 클래스로 묶을수있다)

### 캡슐화

- 비슷한 역할을 하는 필드와 메소드들을 하나로 묶고, 구현 내용을 외부에 감춰 외부 객체에서 객체 내부의 구조를 알지 못하고 객체가 노출한 필드와 메소드만 이용 가능하게 하는것.

### 상속

- 상위 객체의 필드와 메소드를 하위 객체에게 물려줘 하위 객체가 상위 객체의 기능을 사용할 수 있도록 하는 것.

### 다형성

- 같은 이름의 메소드인데 다르게 동작하는것(overloading, overriding)