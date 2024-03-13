# Maven vs Gradle
- 메이븐(Maven), Gradle(그레이들)은 빌드 관리 도구이다.

## 1) 빌드 (Build)
- 소스 코드를 컴파일해 실행할 수 있는 가공물로 변환하는 과정을 말한다.
- 자바를 비롯해 프로젝트에 쓰인 각각의 파일 및 자원(.xml, jpg, properties, ...) 등을 JVM(자바 가상 머신)이나 톰캣 같은 WAS(웹 애플리케이션 서버버가 인식할 수 있도록 패키징하는 과정이다.

## 2) 빌드 관리 도구
- 개발자가 소스코드를 작성해 애플리케이션을 생성할 때, 여러 가지 외부 라이브러리를 가져다 사용한다.
- 사용자가 직접 외부 라이브러리를 관리할 필요 없이 필요한 라이브러리를 자동으로 관리해주는 도구가 빌드 관리 도구이다.
- 초기의 자바 빌드 도구는 아파치 앤트(Apache Ant)를 사용했었다.
	- 스크립트 작성이 많고 라이브러리 간 의존 관리가 되지 않았다.
- 그 이후 Maven과 Gradle을 사용하게 되었다.

## 3) Maven
- 아파치 재단에서 만든 오픈 소스 프로젝트 매니징 도구이다.
- Maven은 프로젝트 빌드, 리포트, 도큐먼트 작업 등을 자동으로 할 수 있다.
- 특징
	- 미리 정해진 빌드 순서인 LifeCycle을 기반으로 작업을 수행한다.
	- 필요한 라이브러리를 pom.xml에 정의하면 해당 라이브러리 실행, 설치에 필요한 다른 라이브러리까지 관리하고 네트워크를 통해 자동으로 내려받는다.
	- 빌드에 대한대부분의 책임을 각 플러그인에 위임한다.
- Lifecycle
	- clean: 빌드 시 생성되었던 산출물을 삭제한다.
	- build: 소스코드를 컴파일하고 관련 파일을 패키징 한 후, 테스트를 거쳐 원격 저장소에 배포한다.
	- site: 프로젝트 문서화 작업을 진행한다.

## 4) Gradle
- Maven의 뒤를 이어 나온 프로젝트 구성 관리 및 범용 빌드 도구이다.
- 특징
	- 필요한 라이브러리를 Maven의 pom.xml보다 훨씬 적은 코드 수로 정의한다.
	- 필요한 라이브러리를 프로젝트 설정 주입 방식(Configuration Injection)으로 정의해 Maven의 상속 구조보다 재상용에 용이하다.
	- 빌드 스크립트를 xml이 아닌 JVM에서 동작하는 Groovy(그루비) 기반의 DSL(Domain Specific Language)을 사용해 작성한다.
		- Groovy는 자바 문법과 유사해 자바 개발자가 쉽게 익힐 수 있다.
		- Gradle Wrapper를 이용하면 Gradle이 설치됮 않은 시스템에서도 프로젝트 빌드가 가능하다.