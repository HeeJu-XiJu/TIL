# module
import를 통해 불러오기 위한 파일

# package
```python
myPackage/
    __init__.py
    math/
        __init__.py
        fibo.py
```
모듈들의 집합인 폴더
패키지 안에 __init__.py 파일이 있어야 패키지로 인식

```python
from myPackage.math import fomula

fomula.pi # 3.14
# fomula 내에 있는 pi = 3.14 출력

fomula = 1234
print(fomula) # 1234
# 변수가 중복되면 마지막 변수만 출력 가능

# 해결방안
from myPackage.math import fomula as f
f.pi # 3.14
```

```python
import myPackage

myPackage.math.fomula.pi
myPackage.math.fomula.my_max(1, 2)
# 매번 위치코드를 작성해줘야 하므로 위와 같이 fomula를 import하는 것이 일반적
```

```python
from myPackage.math.fibo import fib_loop
# 특정함수만 불러오기
from myPackage.math.fibo import *
# * 을 사용할 경우 모든 함수를 불러옴
# 메모리에 부하가 올 수 있기 때문에 사용할 함수만 불러오는 것이 일반적
```

# python 내장 패키지
## math
```python
import math
math.pi
path.e
math.ceil() # 올림
math.floor() # 버림
math.sqrt()
math.factorial()
```
## random
```python
import random
random.random() # 0 이상 1 미만 random
random.randint(1, 10) # 7
```
#### .seed
```python
random.seed(1) # 0.13436424411240122
# 1의 random값을 seed로 고정
```

#### .shuffle
```python
a = [1, 2, 3, 4, 5]
random.shuffle(a) # [4, 2, 5, 3, 1]
```

#### .choice
```python
rcp = ['가위', '바위', '보']
random.choice(rcp) # '가위'
```

#### .sample
```python
random.sample(range(1, 46), 6) # [42, 25, 14, 7, 32, 2]
```

## datetime
```python
from datetime import datetime
datetime.now()
datetime.today()
datetime.utcnow()
```

```python
now = datetime.now()
now.strftime('%Y년 %m월 %d일') # 2023년 10월 11일
now.strftime('%y년') # 23년
```
[refere to page](https://docs.python.org/ko/3/library/datetime.html)
![datetime](image.png)

```python
now.year
now.day
now.weekday() # 2
# 0~6 / 월~일
```

```python
from datetime import timedelta
birth = datetime(2023, 1, 1)
future = timedelta(days=3)
birth + future # datetime.datetime(2023, 1, 4, 0, 0)
```

```python
new_year = datetime(2024, 1, 1)
now = datetime.now()
new_year - now # 81 days, 13:24:15.437777
```
