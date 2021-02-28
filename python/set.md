# set

파이썬이 제공하는 집합을 표현하는 자료형이다. 수학에서 배운 집합과 동일하다.(합집합, 교집합, 차집합 등의 연산이 가능하다)

- [집합 연산 사용](#set-operation)
- [메서드 사용](#set-method)
- [집합 표현식 사용](set expression)

## set operation

내가 고등학교 1학년때 지겹도록 배웠던 집합개념을 파이썬에서는 자료형으로 제공한다. 마찬가지로 집합 연산또한 제공한다.

- [합집합](#union)
- [교집합](#intersection)
- [차집합](#difference)
- [XOR](#symmetric-difference)
- [부분집합](#subset)
- [etc](#etc) : (==, !=, isdisjoint())

[up](#set)

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

[up](#set-operation)

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

[up](#set-operation)

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

[up](#set-operation)

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

[up](#set-operation)

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

[up](#set-operation)

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

[up](#set-operation)

## set method

- [add](#add)
- [remove](#remove) , [discard](#discard) , [pop](#pop) , [clear](#clear)
- [copy](#copy)

[up](#set)

### add

set에 요소를 추가한다. 여기서 단일 요소를 추가한다. 

```python
a = {1, 2, 3, 4}
a.add(5)
print(a)
# {1, 2, 3, 4, 5}

a.add(5, 6)
a.add({3, 4}) 
# 이러한 것들은 오류가 발생
```

[up to set-method](#set-method)

### remove

set에 특정 요소를 삭제하고 set에 요소가 없다면 오류를 발생시킨다.

```python
a = {1, 2, 3, 4}
a.remove(1)
# 1 삭제
a.remove(5)
# 오류 발생
```

[up to set-method](#set-method)

### discard

set에 특정 요소를 삭제하고 set에 요소가 없더라도 그냥 넘어간다.

```python
a = {1, 2, 3, 4}
a.discard(1)
a.discard(5)
# 오류 발생 X
```

[up to set-method](#set-method)

### pop

set에 임의의 요소를 꺼내준다. 만약 빈 set라면 오류를 발생시킨다.

```python
a = {1, 2}
# 꺼내지는 순서는 따로 없음. 
print(a.pop())
# 1
print(a.pop())
# 2
print(a.pop())
# Keyerror : 'pop from an empty set'
```

[up to set-method](#set-method)

### clear

set에 모든 요소를 삭제한다.

```python
a = {1, 2, 3, 4}
a.clear()
print(a)
# set()
```

[up to set-method](#set-method)

### copy

a 와 b 는 같은 set 객체를 가리키지만 c 는 별개의 set 객체를 가리킨다.

```python
a = {1, 2, 3, 4}
b = a
c = a.copy()

print(a is b)
print(a is c)
print(a == b)
print(a == c)
# true
# false
# true
# true
```

![copy-in-set](/python/picture/copy-in-set.png)

```python
b.add(5)
```

![copy-in-set-second](/python/picture/copy-in-set-second.png)

[up to set-method](#set-method)

## set expression

```python
a = {i for i in 'apple'}
# a = set(i for i in 'apple')
print(a)
# {'a', 'l', 'e', 'p'}
```

![first-expression-in-set](/python/picture/first-expreesion-in-set)

```python
a = set(i for i in 'pineapple' if i not in 'apl')
print(a)
# {'e', 'i', 'n'}
```

![second-expression-in-set](/python/picture/second-expression-in-set)

[up](#set)

