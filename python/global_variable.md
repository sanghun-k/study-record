# global variable

- global variable
- local variable

---

## 개념 설명

- global variable : script 전체에서 접근할 수 있는 변수
- global scope : global variable 에 접근할 수 있는 범위
- local variable : variable 을 만든 함수 안에서만 접근할 수 있는 변수
- local scope : local variable 에 접근할 수 있는 범위

```python
# global variable
x = 10
def foo():
    # local variable
    # foo 함수 내에서만 접근할 수 있다
    y = 20
    print(x)
    
foo()

# error : y 에 접근할 수 없다
print(y)
```

## global keywoad 사용

- 함수 내에서 global variable 의 값을 변경하고자 할 때 사용한다

```python
x = 10
def foo():
    x = 20
    print(x)
    
foo()
print(x)
```

```
20
10
```

x 의 값이 다르게 출력되는 것을 볼 수 있다. foo 함수 내부에서 사용된 x 가 global variable 이라는 착각을 할 수 있다. 하지만 이것은 foo 함수 내부의 local variable 이다. **즉, global variable x, foo 함수 내부의 local variable x 별개의 변수가 존재한다.**

우리는 global keywoad를 사용해서 global variable을 다른 함수내에서 사용할 수 있다

```python
x = 10
def foo():
    global x
    x = 20
    print(x)
    
foo()
print(x)
```

```
20
20
```