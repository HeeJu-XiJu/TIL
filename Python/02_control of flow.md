# 제어문

## 조건문(if문)
```python
if <조건식>:
    if의 조건식이 참인 경우 실행하는 코드
else:
    if의 조건식이 거짓인 경우 실행하는 코드

<조건식>의 결과값은 0(false), 1(true)로 자동형변환
```

## 조건문(elif문)
```python
if <조건식>:
    if 조건이 참인 경우 실행
elif <조건식>:
    elif 조건이 참인 경우 실행
.
.
.
else:
    위의 조건식에 하나도 부합하지 않는 경우 실행
```

## 조건표현식
```python
true_value if <조건식> else false_value
```

# 반복문

## while문
```python
while <조건식>:
    실행할 코드
```

## for문
```python
for variable in sequence:
    실행할 코드
```

```python
# index번호와 value를 tuple로 출력
for variable in enumerate(sequence):
    실행할 코드
```

## dictionary 반복문
1. for key in dict:
2. for key in dict.keys():
3. for value in dict.values():
4. for key, value in dict.items():

## break
반복문을 종료시키는 키워드

## continue
continue 이후의 코드를 실행하지 않고 다음 반복을 실행

## else
else문은 끝까지 반복이 진행된 후 실행 (break를 만나지 않은 경우)

## pass

## match
```python
match value:
    case 조건:
        실행할 코드
    case 조건:
        실행할 코드
    case _:
        실행할 코드        
```