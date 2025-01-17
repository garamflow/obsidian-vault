# 해시(Hash), 해시테이블(HashTable)
## 1. 해시(Hash)
- 데이터를 빠르게 찾기 위해 고안된 방법이다.
- 해시 함수를 사용해 데이터를 특정 값으로 매핑한다.

### 해시 함수
- 임의의 길이를 가진 데이터를 고정된 길이의 값으로 변환하는 함수이다.
- 해시 값을 이용해 배열처럼 인덱스를 활용해 데이터를 빠르게 찾을 수 있다.

### 주요 특징
- 빠른 검색
	- 평균적으로 O(1)의 시간 복잡도로 데이터를 검색할 수 있다.
- 충돌
	- 서로 다른 입력이 동일한 해시 값을 가질 수 있는 현상을 말한다.
	- 해결하려면 체이닝과 오픈 어드레싱같은 기술이 필요하다.

## 2. 해시테이블(HashTable)
- 해시 테이블은 데이터를 해시 함수를 사용해 특정 인덱스에 저장하는 자료구조이다.
	- 데이터를 저장하고 검색할 때 해시 값을 사용해 빠르게 처리할 수 있다.
- **해시 테이블 구조**
	- 배열과 연결 리스트를 결합한 형태로, 해시 함수가 반환한 인덱스를 사용해 데이터를 저장한다.
	- 충돌이 발생하면 그 인덱스에 연결 리스트나 다른 방법으로 데이터를 저장한다.

## 3. HashTable vs HashMap
- Java에서 제공하는 해시 기반 자료구조이다.

| 특성             | `HashTable`                              | `HashMap`                                    |
| -------------- | ---------------------------------------- | -------------------------------------------- |
| **동기화 여부**     | `HashTable`은 **동기화**되어 있어 멀티스레드 환경에서 안전함 | `HashMap`은 **동기화**되지 않음. 멀티스레드 환경에서는 안전하지 않음 |
| **null 허용 여부** | `HashTable`은 **null** 값을 허용하지 않음         | `HashMap`은 **null** 키와 값을 허용                 |
| **성능**         | 동기화 때문에 `HashTable`이 **성능이 떨어질 수 있음**    | 동기화가 없으므로 `HashMap`이 더 **빠름**                |
### 코딩테스트에서 `HashTable`과 `HashMap` 선택
- 단일 스레드 환경에서는 보통 `HashMap`을 사용하며, 성능이 더 좋다.
- 멀티스레드 환경에서 안전한 동작이 필요할 경우 `HashTable`을 사용할 수 있다.
	- 그러나 자바 5 이상에서는 `ConcurrentHashMap`을 더 많이 사용한다.

## 4. 코딩테스트에서의 사용 사례
- **해시맵(HashMap)**
    - 빠른 검색, 삽입, 삭제가 필요한 문제에서 자주 사용
        - 예를 들어, 배열에서 중복 요소를 찾거나, 특정 값의 빈도를 계산하는 문제에서 사용된다.
        - 예시) 두 수의 합을 찾는 문제(Two Sum)에서, 배열의 숫자와 인덱스를 `HashMap`에 저장해 빠르게 해결할 수 있다.
- **집합(Set)**
	- `HashSet`은 중복된 값을 허용하지 않는 자료구조로, 중복을 제거하는 문제에서 자주 사용된다.

