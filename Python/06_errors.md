# Error

## syntax error
```python
if True:
    pass
else

##########

  Cell In[1], line 3
    else
        ^
SyntaxError: expected ':'
```

```python
print('hi'

##########

  Cell In[2], line 1
    print('hi'
              ^
SyntaxError: incomplete input
```

```python
if True print('hello')

##########

  Cell In[3], line 1
    if True print('hello')
            ^
SyntaxError: invalid syntax
```

## exception
```python
print(5/0)

##########

Cell In[4], line 1
----> 1 print(5/0)

ZeroDivisionError: division by zero
```

```python
print(hello)

##########

Cell In[5], line 1
----> 1 print(hello)

NameError: name 'hello' is not defined
```

```python
1 + '1'

##########

Cell In[6], line 1
----> 1 1 + '1'

TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

```python
'1' + 1

##########

Cell In[7], line 1
----> 1 '1' + 1

TypeError: can only concatenate str (not "int") to str
```

```python
import random
random.sample([1, 2, 3, 4])
# random.sample([1, 2, 3, 4], 2)

##########

Cell In[12], line 1
----> 1 random.sample([1, 2, 3, 4])
      2 # random.sample([1, 2, 3, 4], 2)

TypeError: Random.sample() missing 1 required positional argument: 'k'
```

```python
import random
random.sample([1, 2, 3, 4], 2, 2, 2, 2)
# random.sample([1, 2, 3, 4], 2)

##########

Cell In[14], line 1
----> 1 random.sample([1, 2, 3, 4], 2, 2, 2, 2)
      2 # 3개의 인자를 넣어야 하는데 6개 넣었다

TypeError: Random.sample() takes 3 positional arguments but 6 were given
```

```python
int('4.5')

##########

Cell In[15], line 1
----> 1 int('4.5')

ValueError: invalid literal for int() with base 10: '4.5'
```

```python
numbers = [1, 2, 3, 4]
numbers.index(100)

##########

Cell In[19], line 2
      1 numbers = [1, 2, 3, 4]
----> 2 numbers.index(100)

ValueError: 100 is not in list
```

```python
numbers = [1, 2, 3, 4]
numbers[100]

##########

Cell In[20], line 1
----> 1 numbers [1, 2, 3, 4]
      2 numbers[100]

TypeError: list indices must be integers or slices, not tuple
```

```python
my_dict = {
    'apple': '사과',
    'banana': '바나나',
}
my_dict['melon']

##########

Cell In[21], line 5
      1 my_dict = {
      2     'apple': '사과',
      3     'banana': '바나나',
      4 }
----> 5 my_dict['melon']

KeyError: 'melon'
```

```python
import asdf

##########

Cell In[22], line 1
----> 1 import asdf

ModuleNotFoundError: No module named 'asdf'
```

```python
while True:
    continue
# 코드를 중지시켜야 하는 상황(ctrl + c)

##########

Cell In[21], line 2
      1 while True:
----> 2     continue

KeyboardInterrupt: 
```

## 예외처리
```python
try:
    code
except 예외:
    code
```

```python
try:
    num = int(input('100을 나눌 값을 입력해주세요 : '))
    print(f'100을 {num}으로 나누면 {100/num}입니다.')
except (ValueError, TypeError):
    print('입력한 정보는 숫자가 아닙니다.')
except ZeroDivisionError as err:
    print('수학적으로 0으로는 나눌 수 없습니다.')
    print(err) # error 사유도 함께 출력가능
except:
    print('무엇인가 잘못되었습니다.') # except는 맨마지막에 배치)
```

### else
예외를 일으키지 않을 때 실행되는 코드

```python
try:
    numbers = [1, 2, 3]
    num = numbers[2]
except:
    print('오류발생')
else:
    print(num ** 3)
# 27
```

### finally
예외 상황과 무관하게 무조건 최종적으로 실행되는 코드
```python
try:
    numbers = [1, 2, 3]
    num = numbers[100]
except:
    print('오류발생')
finally:
    print('end')

# 오류발생
# end
```

### raise
예외를 강제로 발생시키는 상황에서 사용

```python
for i in range(100):
    if i == 50:
        print(i)
        raise

#########
Cell In[51], line 4
      2 if i == 50:
      3     print(i)
----> 4     raise

RuntimeError: No active exception to reraise
```