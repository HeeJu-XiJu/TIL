### input.txt 불러오기
```python
import sys
sys.stdin = open('input.txt')
```

### input() 관련
```python
T = int(input())

for tc in range(1, T+1):
    code
```

list로 불러오기
```python
numbers = list( map( int, input().split()))
```


## command
소문자 확인

`변수.islower()` => `True` / `False`

indoex number 확인

`sequence.index(value)`

알파벳 여부 확인

`변수.isalpha()` => `True` / `False`

대소문자 확인

`변수.upper()` `lower()` => `True` / `False`

아키코드 확인

`ord(변수)`

list로 정리

```python
sequence = []
sequence.append(변수)
```

list의 value만 출력
'변수 사이 넣을 문자',join(sequnece)