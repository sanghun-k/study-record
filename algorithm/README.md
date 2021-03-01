# Study algorithm
알고리즘 공부하면서 정리하자.
- [sorting algorithm](#sorting)

## sorting
- 원소들을 일정한 순서대로 열거하는 알고리즘이다.
- 효율적인 정렬은 탐색 or 병합 알고리즘처럼 정렬된 리스트에서 바르게 동작하는 다른 알고리즘을 최적화하는 데 중요하다.
- 정렬 알고리즘의 결과가 만족해야하는 조건
	- 출력은 오름차순이다.
	- 출력은 입력을 재배열하여 만든 순열이다.
---
- [시간 복잡도](#시간-복잡도)

### 시간 복잡도
|sorting|worst-case(O)|average-case(𝚯)|worst-case(Ω)|
|----------------|:--------:|:--------:|:--------:|
|[quick sorting](quick_sorting.md)|n<sup>2</sup>|nlogn|nlogn|
