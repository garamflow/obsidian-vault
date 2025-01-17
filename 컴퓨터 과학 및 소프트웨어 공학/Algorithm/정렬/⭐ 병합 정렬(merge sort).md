# ⭐ 병합 정렬(merge sort)
- 분할 정복 방식을 사용해 데이터를 분할하고 분할한 집합을 정렬하며 합치는 알고리즘이다.
	- 항상 반으로 쪼갠다.
- 병합 정렬의 시간 복잡도는 O(nlogn)이다.
- 코딩 테스트의 정렬 관련 문제에서 자주 등장한다.
	- **2개의 그룹을 병합하는 원리**는 꼭 숙지해야한다.

## 병합 정렬의 핵심 이론
- 부분 그룹을 `setN`이라고 표시한다.
- 가장 작은 데이터 집합으로 분할한다.
- 병합하면서 정렬을 계속 진행한다.
	- set1+set2 를 병합해서 정렬한다.
	- set3+set4 를 병합해서 정렬한다.
	- ...

## 2개의 그룹을 병합하는 과정
- 투 포인터의 개념을 사용하여 왼쪽, 오른쪽 그룹을 병합한다.
- 왼쪽 포인터와 오른쪽 포인터의 값을 비교하여 작은 값을 배열에 추가하고 포인터를 오른쪽으로 1칸 이동시킨다.
- 한 그룹이 모두 뽑혔다면 다른 그룹의 나머지는 뒤에 붙여주면 된다.
![병합 정렬](/media/컴퓨터%20과학%20및%20소프트웨어%20공학/Algorithm/병합%20정렬.png)

## 정렬되지 않은 그룹을 정렬시키기
```java
[4, 2, 6, 3, 7, 8, 5, 1]
> [4, 2, 6, 3] / [7, 8, 5, 1]
> [4, 2] / [6, 3] / [7, 8] / [5, 1]
> [4] / [2] / [6] / [3] ...
> [2, 4] / [3, 6] ...
> [2, 3, 4, 6], ...
```
1. 배열을 나눠서 배열이 1개씩 남을 때 까지 쪼갠다.
2. 이제 방 하나씩을 비교해서 더 큰 배열로 합쳐줄 때 작은 수를 먼저 넣어간다.

## 병합 정렬 구현
```java
public class Main {
	private static void mergeSort(int[] arr) {
		int[] tmp = new int[arr.length];
		mergeSort(arr, tmp, 0, arr.length - 1);
	}

	private static void mergeSort(int[] arr, int[] tmp, int start, int end) {
		if (start < end) {
			int mid = (start + end) / 2;
			mergeSort(arr, tmp, start, mid);
			mergeSort(arr, tmp, mid + 1, end);
			merge(arr, tmp, start, mid, end);
		}
	}

	private static void merge(int[] arr, int[] tmp, int start, int end) {
		for (int i = start; i <= end; i++) {
			tmp[i] = arr[i];
		}

		int part1 = start;
		int part2 = mid + 1;
		int index = start;

		while (part1 <= mid && part2 <= end) {
			if (tmp[part1] <= tmp[part2]) {
				arr[index] = tmp[part1];
				part1++;
			} else {
				arr[index] = tmp[part2];
				part2++;
			}
			index++;
		}

		for (int i = 0; i <= mid - part1; i++) {
			arr[index + i] = tmp[part1 + i];
		}
	}

	public static void main(String[] args) {
		int[] arr = {3, 9, 4, 7, 5, 0, 1, 6, 8, 2};
		mergeSort(arr);
	}
}
```