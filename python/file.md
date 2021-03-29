# file

- [흐름](#simple-flow)
- [Write](#file-write)
- [Read](#file-read)
- [Tip : 파일 열기, 닫기 동시에](#file-open-and-close)
- [Tip : 파일 읽기](#file-read-iterator)

## simple flow

1. file open
2. get file object
3. read or write
4. file close

open method로 file object를 얻은 후에 write or read를 한다. file에 대한 볼일이 끝나면 close로 file object를 닫아준다.

```python
# write 목적으로 file object 를 얻는다
file = open('hello.txt', 'w')
file.write('hello world!')
file.close()

# read 목적으로 file object 를 얻는다
file = open('hello.txt', 'r')
s = file.read()
file.close()
print(s)
```

## file write

### write

```python
with open('hello1.txt', 'w') as f:
    for i in range(3):
        f.write('hello world! {0}\n'.format(i))

# wirte 하는 문자열 끝에 개행문자가 없다면??
with open('hello2.txt', 'w') as f:
    for i in range(3):
        f.write('hello world! {0}'.format(i))
```

```plain text
# hello1.txt
hello world! 0
hello world! 1
hello world! 2

# hello2.txt
hello world! 0hello world! 1hello world! 2
```

---

### writelines

list에 있는 문자열들을 file object에 쓸 수 있다.

```python
l = ['hello\n', 'my name is\n', 'kim\n']

with open('hello.txt', 'w') as f:
    f.writelines(l)
```

> writelines도 마찬가지로 list에 있는 문자열 끝에 개행문자가 없다면 한줄로 써질 것이다.

## file read

```plain text
# hello.txt
hello
My name is
Kim
```

### read

```python
with open('hello.txt', 'r') as f:
    s = f.read()
    print(s)
```

```consol
hello
My name is
Kim
```

파일 전체의 문자열을 하나의 문자열 객체로 보고 s가 가리키게 한다. 

### readline

```python
with open('hello.txt', 'r') as f:
    line = None
    while True:
		line = f.readline()
        if line == '':
            break
        print(line)
```

```consol
hello
My name is
Kim
```

파일의 문자열을 한줄씩 읽어온다

### readlines

```python
with open('hello.txt', 'r') as f:
    lines = f.readlines()
print(lines)
```

```consol
['hello\n', 'My name is\n', 'Kim\n']
```

파일의 문자열들을 하나의 리스트에 담는다

## file open and close

```python
with open(file name, file mode) as f:
    code

# f.close() 를 따로 해주지 않아도 자동으로 닫아준다
with open('hello.txt', 'r') as f:
	s = f.read()
    print(s)
```

## file read iterator

```python
with open('hello.txt', 'r') as f:
    for line in f:
        print(line.strip('\n'))
```

```consol
hello
My name is
Kim
```

