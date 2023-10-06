# 함수(function)

## 함수의 선언과 호출
### 함수의 선언
```python
def func_name(parameter1, parameter2):
    code1
    code2
    .
    .
    .
    return value
```

### 함수의 호출(실행)
```python
func_name(parameter1, parameter2)
```

### 함수의 return
- 함수가 return을 만나면 해당 값을 반환하고 함수를 종료
- 만약 return이 없다면 None을 자동 반환
- return은 오직 하나의 객체만 반환

```python
def my_max2(num1, num2):
    return 'hello' 
    
    if num1 > num2:
        return num1

# 출력값은 num1이 아닌 'hello' (처음 만난 return값 반환)
```

```python
def my_func(number):
    print('hello')

# 출력값은 none (return이 없기 때문)
```

## 함수의 인수

### 위치인수
기본적으로 함수는 인수의 위치로 판단

```python
func(num1, num2)
func(num2, num1) 
두 값은 다른 출력값을 가짐
```

### 기본값
기본값이 있는 인자를 뒤쪽으로 배치
```python
def func(p1, p2=v2):
    code
    .
    .
    .
    return p1, p2
```
```python
def greeting(age, name='익명')
    return f'{age}살 {name}님 안녕하세요!!'

# print(greeting(10)) => 10살 익명님 안녕하세요!!
```

### 키워드 인자
함수를 호출(실행)할 때 내가 원하는 위치에 직접적으로 특정인자를 전달 가능

```python
print(greeting(name='홍길동', age=30))
```

### 가변 인자 리스트
```python
def func(*parms):
    code
    .
    .
    .
```

```python
def my_print(*words):
    print(words)

# my_print('a', 'b', 'c') 
# => {'a', 'b', 'c'} Tuple형태로 반환
```

### 정의되지 않은 키워드 인자
```python
def func(**kwargs):
    code
    .
    .
    .
```

```python
def fake_dict(**kwargs):
    print(kwargs)

# fake_dict(a=10, b=20) 
# => {'a': 10, 'b': 20} dict로 출력
```

### dictionary를 인자로 넣기(unpacking)
```python
def sign_up(id, pw, pw_confirmation):
    if pw == pw_confirmation:
        print(f'{id}님 회원가입이 완료되었습니다.')
    else:
        print('비밀번호가 일치하지 않습니다.')
```
```python
account = {
    'id': 'change',
    'pw': '1234',
    'pw_confirmation': '1234',
}
sign_up(**account)
=> change님 회원가입이 완료되었습니다.
```

### lambda 표현식
일회성(임시) 함수

```python
lambda parameter: expression
```

### 타입힌트
```python
# 인자 타입을 힌트로 제공
def my_sum(a: int, b: int):
    return a + b
```

### 이름공간(scope)
python에서 사용되는 이름들은 이름공간(namespace)에 저장
- Local scope : 정의된 함수 내부
- Enclosed scope : 상위 함수
- Global scope : 함수밖의 변수 혹은 ijmport된 모듈
- Built-in scope : python이 기본적으로 가지고 있는 함수 혹은 변수

### 재귀(recursive)
재귀함수는 함수 내부에서 자기 자신을 호출하는 함수

ex. 팩토리얼, 피보나치 수열 등

계산이 오래 걸린다는 단점이 있음