# pickle

파일에 문자열이 아니라 객체를 저장할 수 있다.

- pickling : 파일에 객체를 저장
- unpickling : 파일로부터 객체를 읽기

```python
import pickle
 
name = 'james'
age = 17
address = '서울시 서초구 반포동'
scores = {'korean': 90, 'english': 95, 'mathematics': 85, 'science': 82}
 
with open('james.txt', 'wb') as file:    # james.p 파일을 바이너리 쓰기 모드(wb)로 열기
    pickle.dump(name, file)
    pickle.dump(age, file)
    pickle.dump(address, file)
    pickle.dump(scores, file)
```

```python
import pickle

with open('james.txt', 'rb') as file:    # james.p 파일을 바이너리 읽기 모드(rb)로 열기
    name = pickle.load(file)
    age = pickle.load(file)
    address = pickle.load(file)
    scores = pickle.load(file)
    print(name)
    print(age)
    print(address)
    print(scores)
```

```consol
james
17
서울시 서초구 반포동
{'korean': 90, 'english': 95, 'mathematics': 85, 'science': 82}
```

