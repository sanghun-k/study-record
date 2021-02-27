# set

파이썬이 제공하는 집합을 표현하는 자료형이다. 수학에서 배운 집합과 동일하다.(합집합, 교집합, 차집합 등의 연산이 가능하다)

- [집합 연산 사용](set-operation)

## set operation

내가 고등학교 1학년때 지겹도록 배웠던 집합개념을 파이썬에서는 자료형으로 제공한다. 마찬가지로 집합 연산또한 제공한다.

- [합집합](union)
- [교집합](intersection)
- [차집합](difference)
- [XOR](symmetric-difference)
- [부분집합](subset)
- [etc](etc) : (==, !=, isdisjoint())

[up](set)

### union

- set1 | set2
- set.union(set1, set2)

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a|b)
print(set.union(a, b))
# {1, 2, 3, 4, 5, 6}
```

[up](set-operation)

### intersection

- Set1 & set2
- set.intersection(set1, set2)

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a&b)
print(set.intersection(a, b))
# {3, 4}
```

[up](set-operation)

### difference

- set1 - set2
- set.difference(set1, set2)

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a-b)
print(set.difference(a, b))
# {1, 2}
```

[up](set-operation)

### symmetric difference

- set1 ^ set2
- set.symmetric_diffence(set1, set2)

```python
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a^b)
print(set.symmetric_difference(a, b))
# {1, 2, 5, 6}
```

[up](set-operation)

### subset

- <, <=, >, >=

```python
a = {1, 2, 3, 4}
b = {2, 4}
c = {3, 6}
print(a > b)
# a.issuperset(b)
# true : a가 b의 상위집합인지 묻는다.
print(a < b)
# a.issubset(b)
# false : a가 b의 하위집합, 즉 부분집합인지 묻는다
```

[up](set-operation)

### etc

```python
# set 같은지 확인
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a==b)
# false
print(a!=b)
# true
```

```python
# 겹치는 요소가 없는지 확인한다.
a = {1, 2, 3, 4}
b = {3, 4, 5, 6}
print(a.isdisjoint(b))
# false : 3, 4 가 겹침
print(a.isdisjoint({5, 6, 7, 8}))
# true
```

[up](set-operation)

