# 객체 지향 프로그래밍
# object-oriented

![java](https://github.com/networkSorcerer/object-oriented/assets/155520035/d221aef6-d3a1-4c48-903e-a69f7aea2e05)
![이클립스](https://github.com/networkSorcerer/object-oriented/assets/155520035/57fdd3ab-4790-4813-9742-5c8c5d0fdfef)

## 구조로 알아 보는 JVM의 동작 원리

### 1. 클래스 파일 
- 개발자가 만드는 혹은 이미 만들어진 프로그램
- 개발할 자바 프로그래은 파일 확장자가 '.java'
- '.java' 파일이 자바 컴파일러에서 컴파일 과정을 거치면 '.class'파일이 생성
- 컴파일 과정을 거쳐 생성된 클래스 파일은 JVM에서 실행 가능
- 클래스 파일이 서로 유기적으로 동작하면서 프로그램은 자기의 기능을 수행

### 2. 클래스 로더 서브 시스템
- 자바 클래스 파일들은 OS에서 직접 동작하는 것이 아니라 JVM 위에서 동작
- JVM은 실행할 클래스 파일을 읽고, JVM 메모리에 올려놓는 과정이 필요
- 이 과정을 클래스 로딩이라 하며 JVM의 클래스 로더 서브 시스템이 담당
- 클래스 로더 서브 시스템을 줄여서 클래스 로더라 부름
- 동적 로딩 : 프로그램을 실행하는 도중에 새로운 클래스를 로딩할 수 있음
- 로드 타임 동적 로딩 : 프로그램 실행 초기에 클래스를 로딩하는 것
- 런타임 동적 로딩 : 프로그램 실행 중간에도 클래스를 로딩하는 것

### 실행 데이터 영역
- 클래스 로더로부터 분석된 데이터를 저장하고 실행 도중 필요한 데이터를 저장하는 영역
- 메모리에 올라간 클래스, 객체, 변수들이 저장되는 곳
- 데이터의 목적과 종류에 따라서 메모리를 효율적으로 관리하기 위해 5개 영역으로 구분

### 메소드 영역
- 클래스 로더에 의해서 로딩된 클래스가 저장되는 곳
- JVM에서 클래스를 실행하면 메소드 영역에서 클래스 정보를 복사
- 메소드 영역은 JVM 메모리 영역 중 가장 먼저 데이터가 저장되는 영역

### 스택 영역
- 호출된 (실행된) 메소드 정보가 저장되는 곳, 실행이 끝나면 저장된 정보는 삭제
- 메소드가 실행 될때마다 저장되는 메소드 정보에는 매개변수, 지역 변수등
- 이 영역에서는 스택을 데이터 관리 방법으로 사용
- 스택은 LIFO 방식으로 동작
- 메소드의 호출 정보나 호출 순서등을 추적하기 편리

### 힙 영역
- JVM의 실행 데이터 영역 중에서 가장 중요한 역할을 담당
- 객체는 클래스가 실행될때 생성되어서 힙 영역에 저장
- 힙 영역은 JVM에서 가장 중요한 데이터를 저장함과 동시에 세밀한 관리가 이뤄지는곳
- 힙 영역은 동적으로 데이터가 생성되고 소멸되는 영역
- 클래스를 실행하면 데이터가 저장되는 영역, 프로그램 실행에 영향을 미칠 수도 있음

### 레지스터 영역
- 현재 JVM이 수행할 명령어의 주소를 저장하는 메모리 공간

### 네이티브 메소드 스택 영역
- 네이티브 메소드 : OS의 시스템 정보, 리소스를 사용하거나 접근하기 위한 코드
- 이러한 매개 변수나 지역 변수등 네이티브 메소드를 위한 영역으로 이에 대한 정보가 저장
- 자바 프로그램과 OS사이에 JVM이 존재, 자바프로그램은 시스템에 직접 접근하기 어려움
- JNI API를 사용하면 자바 프로그램에서 OS시스템에 대한 접근이 가능

## 객체 지향 방법론
- 하나 이상의 데이터와 기능을 묶어 객체라 하고, 데이터의 변경에 해당 객체만 영향을 받도록 분리하는 방법론이 바로 객체 지향 방법론이다
- 객체 지향 개발 방법론의 핵심은 개체이다
- 객체간에는(결합도) 연관성이 낮아야 하고, 객체 내 요소간(응집도)에는 연관성이 높아야 한다
- OOP : 현실 세계에서 어떤 제품을 만들 때 부품을 먼저 개발하고 이 부품들을 하나씩 조립해서 완성된 제품을 만들듯이, 소프트웨어를 개발 할 때에도 부품에 해당하는 객체들을 먼저 만들고 이것들을 하나씩 조립해서 완성된 프로그램을 만드는 기법( 모든 관점을 객체라는 단위로 바라본다)
- 객체 = 속성 + 동작

## 클래스
- 클래스 선언 : 클래스는 객체(object)를 만드는 틀
- 필드 선언 : 필드는 객체의 속성(특징)을 나타 냄
- 메서드 선언 : 메서드는 객체의 동작은 나타냄
- 접근 제한자 : private(외부의 접근 차단), (default)(접근 제한자를 생략했을 때 자동으로 지정), protected(접근 권한은 같은 패키지로 제한, 클래스끼리 서로 상속 관계로 연결 되어 있을 시 다른 패키지에서도 접근 가능), public(누구나 접근 가능)

## 인스턴스 화
- 클래스를 이용해서 실제인 객체를 생성하는 과정을 인스턴스 화 라고 한다. 그리고 메모리에 생성된 객체, 즉 실체를 인스턴스라고 한다
### 객체의 생성
```java
myCar = new Car();
```
