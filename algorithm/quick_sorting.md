# quick sorting

## 위키백과

- 비교 정렬에 속한다
- 최악의 경우 O(n<sup>2</sup>) 평균의 경우 O(nlog n)
- 퀵 정렬의 내부 루프는 대부분의 컴퓨터 구조에서 효율적으로 작동하도록 설계
  - 이유 : 메모리 참조가 지역화되어 있기 때문에 CPU 캐시 히트율이 높아지기 때문
- 데이터를 정렬할 때 제곱 시간이 걸릴 확률이 거의 없도록 알고리즘을 설계하는 것이 가능하다.
- 또한 매 단계에서 적어도 1개의 원소가 자기 자리를 찾기 때문에 정렬할 개수가 줄어든다.
  - 이러한 이유로 다른 O(nlog n) 알고리즘에 비해 훨씬 빠르게 동작한다.
  - quick sort 이름의 기원
- O(log n) 만큼의 메모리를 필요로 한다.
- 원소들 중에 같은 값이 있는 경우 같은 값들의 정렬 이후 순서가 초기 순서와 달라질 수 있어 불완전 정렬에 속한다.



- divide and conquer
  1. pivot 설정
  2. pivot을 기준으로 앞에는 작은 값이, 뒤에는 큰 값이 오도록 정렬 => partition . 이후에는 pivot은 자리가 고정이 되고 움직이지 않는다.
  3. 나뉜 2개의 리스트를 각자 재귀적으로 위의 과정을 반복한다. => 리스트의 크기가 0 or 1이 될때까지 수행한다.
- 재귀 호출이 한 번 진행될 때마다 최소한 하나의 원소는 최종적으로 위치가 정해지므로, 이 알고리즘은 반드시 끝난다는 것을 보장할 수 있다.



```pascal
function partition(a, left, right, pivotIndex)
	pivotValue := a[pivotIndex]
	swap(a[pivotIndex], a[right]) // 피벗을 끝으로 옮겨 놓는다.
	storeIndex := left
	for i from left to right-1
		if a[i] <= pivotValue then
			swap(a[storeIndex], a[i])
			storeIndex := storeIndex + 1
	swap(a[right], a[storeIndex]) // 피벗을 두 리스트 사이에 위치시킨다.
	return storeIndex

function quicksort(a, left, right) // 퀵정렬 함수 호출
	if right > left then // list의 원소 최소 2개이상 존재
		select a pivot value a[pivotIndex] // pivot 을 설정한다
		pivotNewIndex := partition(a, left, right, pivotIndex) // partition 후에 pivot 이 위치한 index
		// 재귀적으로 수행한다. 
		quicksort(a, left, pivotNewIndex-1) // pivot 중심으로 왼쪽 리스트
		quicksort(a, pivotNewIndex+1, right) // pivot 중심으로 오른쪽 리스트
```

