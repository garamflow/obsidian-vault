# @Data
## 1) `@Data`란?
- Lombok 라이브러리에 속한 어노테이션이다.
- 클래스 레벨에서 사용되며, 다음과 같은 기능을 제공합니다:
	- 모든 필드에 대한 getter 메서드
	- 모든 non-final 필드에 대한 setter 메서드
	- toString 메서드
	- equals와 hashCode메서드
- 이 어노테이션을 사용하면 클래스의 멤버 변수(필드)에 대한 기본적인 메서드를 자동으로 생성해주어, 유지보수하기 쉽게 합니다.

## 2) 언제 사용하는가?
- `@Data`는 단순한 데이터 객체 (POJOs: Plain Old Java Objects)에 대해 반복적인 메서드를 자동으로 생성할 때 사용한다.
- 코드의 양을 줄이고 가독성을 향상시킬 수 있다.