# 딕셔너리

딕셔너리는 **key: value 쌍의 순서 없는 집합**으로 생각할 수 있다.

딕셔너리는 key를 이용해서 그에 대응되는 value를 찾을 수 있다. 이것이 딕셔너리의 주 연산이다.

- [method](#method)
- [소소한 이용](#using)

## 딕셔너리 선언하기

딕셔너리를 만들기 위한 큰 틀이 2개가 존재한다.

- dict()
- {}

```python
a = dict(one=1, two=2, three=3)
b = dict('one': 1, 'two': 2, 'three': 3)
c = dict(zip(['one', 'two', 'three'], [1, 2, 3]))
d = dict([('one', 1), ('two', 2), ('three', 3)])
e = {'three': 3, 'one': 1, 'two': 2}

# 같은지 확인해본다
print(a==b==c==d==e)
```

## key - value

value에는 모든 자료형이 올 수 있다. 하지만 key에는 리스트, 딕셔너리 등 객체의 내용물이 변할 수 있는 자료형은 올 수 없다.

## method

- [list(d)](#list) : d에 있는 keys로 이루어진 리스트를 준다
- [len(d)](#len) : d에 있는 \<key-value\> 쌍의 수를 준다
- [d[key]](#d) : d에 해당 key에 대응되는 value를 준다. 없으면 keyerror
- [del d[key]](#del) : d에 해당 \<key-value\> 를 제거한다. 없으면 keyerror
- [get(key[, default])](#get) : key에 대응되는 value를 준다. 없으면 default를 준다 (변경 가능). default를 따로 주지 않는다면 None을 준다
- [items()](#items) : 딕셔너리에 있는 모든 \<key-value\> 를 준다 (list)
- [keys()](#keys) : 딕셔너리에 있는 모든 keys를 준다 (list)
- [values()](#values) : 딕셔너리에 있는 모든 values를 준다 (list)
- [pop(key[, default])](#pop-popitem) : \<key-value\> 쌍을 뽑아준다. 없으면 default를 준다 (변경 가능). default를 따로 주지 않는다면 keyerror
- [popitem()](#pop-popitem) : LIFO 형태로 \<key-value\> 쌍을 뽑아준다. 없으면 keyerror (3.7 이전 버전에서는 임의의 \<key-value\> 를 꺼내준다)
- [setdefault(key[, value])](#setdefault-update) : \<key-value\> 쌍을 추가해준다. value가 주어지지 않는다면 (key, None) 으로 추가해준다
- [update(key: value)](#setdefault-update) : (key, value) 를 수정 or 추가해준다.

- [back](#딕셔너리)

### pop popitem

```python
# 실행환경 3.7
a = dict([('a', 1), ('b', 2), ('c', 3), ('d', 4)])
print(a.pop('a'))
print(a.pop('e', 'no find'))
print(a.popitem())
```

```python
1
no find
('d', 4)
```

[to method](#method)

### values

```python
a = dict({'a': 1, 'c': 3, 'b': 2})
print(a.values)
```

```python
[1, 2, 3]
```

[to method](#method)

### keys

```python
a = {'a': 1, 'b': 2, 'c': 3}
print(a.keys())
```

```python
['a', 'b', 'c']
```

[to method](#method)

### items

```python
a = dict([['a', 'b', 'c'], [1, 2, 3]])
b = a.itmes()
print(b)
```

```python
[('a', 1), ('b', 2), ('c', 3)]
```

[to method](#method)

### get

```python
a = dict([('a': 1), ('b': 2), ('c': 3)])
print(a.get('a'))
print(a.get('d', 'no find'))
```

```python
1
no find
```

[to method](#method)

### setdefault update

- setdefault : \<key-value\> 추가.
- update : \<key-value\> 수정. 해당 key가 딕셔너리에 없다면 추가

> setdefault는 \<key-value\> 를 추가만 가능하다. 수정은 불가!!

```python
a = dict(zip(['a', 'b', 'c', 'd'], [1, 2, 3, 4]))

# setdefault(key, value)
a.setdefault('e')
a.setdefault('f', 6)

# update(key=value)
a.update(e=5)
a.update(g=7)

print(a)
```

```python
a = dict()
a.update(zip(['a', 'b'], [1, 2]))
```

[to method](#method)

### list

```python
a = dict([['a', 1], ['b', 2], ['c', 3]])
print(list(a))
```

```python
['a', 'b', 'c']
```

[to method](#method)

### len

```python
a = {'a': 1, 'b': 2, 'c': 3}
print(len(a))
```

```python
3
```

[to method](#method)

### d

```python
a = dict(a=1, b=2, c=3)
print(a['a'])
```

```python
1
```

[to method](#method)

### del

```python
a = dict(zip(['a', 'b', 'c'], [1, 2, 3]))
del a['a']

print(a)
```

```python
{'c': 3, 'b': 2}
```

[to method](#method)

## using

- [for문에서 key, value 가져오기](#in-for-loop)
- [for문, if문으로 딕셔너리 만들기](#make-dict-using-for-if-statement)
- [중첩 딕셔너리](#nested-dictionary)
- [복사](#copy)

- [back](#딕셔너리)
### in for loop

key, value 를 가지고 올 때 

```python
x = dict(zip(['a', 'b', 'c'], [1, 2, 3]))

# key 
# for key in x.keys(): 가능
for key in x:
    print(key, end=' ')
print()

# key, value
for key, value in x.items():
    print("{}: {}".format(key, value), end=' ')
print()

# value
for value in x.values():
    print(value, end=' ')
```

[to using](#using)

### make dict using for if statement

컴프리헨션을 이용해서 dict를 만들 수 있다.

> dict클래스 메서드를 사용할 수 있다. 
>
> dict.fromkeys(iterable keys[, default]) : iterable keys 를 받아서 딕셔너리를 만든다. 그들의 value 값을 줄 수 있고 주어지지 않는다면 모두 None으로 해서 만든다.

```python
keys = ['a', 'b', 'c', 'd']
x = {key: value for key, value in dict.fromkeys(keys).items()}
y = {key: value for key, value in dict.fromkeys(keys, 0).items()}
z = {key: 0 for key, value in dict.fromkeys(keys).items()}

print(x)
print(y)
print(z)
```

```python
{'a': None, 'b': None, 'c': None, 'd': None}
{'a': 0, 'b': 0, 'c': 0, 'd': 0}
{'a': 0, 'b': 0, 'c': 0, 'd': 0}
```

for 문내에서 \<key, value\> 쌍을 지울 수 있을까? 답은 No이다. 딕셔너리의 크기가 변했다는 오류가 발생한다

```python
x = {'a': 1, 'b': 2, 'c': 3, 'd': 4}

for key, value in x.items():
    if value == 2:
        del x[key]
print(x)
```

```python
Traceback (most recent call last):
  File "main.py", line 3, in <module>
    for key, value in x.items():
RuntimeError: dictionary changed size during iteration
```

```python
x = {'a': 1, 'b': 2, 'c': 3, 'd': 4}
x = {key: value for key, value in x.items() if value != 2}
print(x)
```

```python
{'a': 1, 'c': 3, 'd': 4}
```

[to using](#using)

### nested dictionary

딕셔너리의 value 값으로 딕셔너리를 가질 수 있다.

```python
coin = {
  'bitcoin': {
    'creator': 'satoshi',
    'price': 100000000
  },
  'etherium': {
    'creator': 'vitarlik',
    'price': 2000000
  },
  'eos': {
    'creator': 'dan',
    'price': 3400
  }
}

for coin_name in coin.keys():
  print("""\
  name : {}
  creator : {}
  price : {}
  """.format(coin_name, coin[coin_name]['creator'], coin[coin_name]['price']))
```

[to using](#using)

### copy

copy를 할 때 신경써야하는 부분이 있다. value로 list, dict 등 내용물을 수정할 수 있는 자료형이 있을 때 이러한 딕셔너리를 copy를 한 후에 한쪽 딕셔너리에서 해당 value를 수정한다면 다른 딕셔너리에서도 똑같이 수정된다. 이를 방지하기 위해 완전 새로운 객체로 만들어주는 copy 모듈에서 deepcopy를 사용할 수 있다. 그렇지만 value로 수정되지 않는 문자열이나 숫자 등이 온다면 copy로도 충분히 사용할 수 있다.

```python
import copy

x = {'a': {'python': 2.7}, 'b': {'python': 3.6}}
y = x.copy()
z = copy.deepcopy(x)

print(x)
print(y)
print(z)
x['a']['python'] = 2.75
print()
print(x)
print(y)
print(z)
```

![스크린샷 2021-02-07 오후 11.47.32](/python/picture/copy-in-dictionary.png)

그림을 보면 x, y의 value가 같은 객체를 가리키고 있는 것을 볼 수 있다. 반면 z의 value는 독립된 객체를 가짐을 볼 수 있다.

[to using](#using)
