# intro
python 개념 정리

![참고문건](https://docs.python.org/ko/3/tutorial/index.html)

## 1. 변수
- `변수이름 = 값`

1. Number
    - `int` : 정수
    - `float` : 소수
    - `complex` : 허수
        - `변수.image` : 허수부분
        - `변수.real` : 실수부분

2. Boolean
    - `True(1)`
    - `False(0)`

3. None
    - `none`

4. String
    - `' '`
    - code 입력 시 `/n` enter, `/t` tab을 의미
    - string interpolation
        1. `%-fomatting` : 

            print('홍길동은 %s살입니다.' % age)
        2. `str.format()` : 

            print('홍길동은 {}살입니다.' .format(age))
        3. `f-string` : 

            print(f'홍길동은 {age}살입니다.')

## 2. 연산자
1. 산술연산자
    - `a + b`
    - `a - b`
    - `a * b`
    - `a / b`
    - `a ** b` : 제곱
    - `a // b` : 나눈 몫
    - `a % b` : 나눈 나머지
    - `divmod(a, b)` : a 나눈 몫, b 나눈 나머지

2. 비교연산자
    - `a > b`
    - `a < b`
    - `a >= b`
    - `a <= b`
    - `a == b`
    - `a != b`

3. 논리연산자
    - `and` : 양쪽 모두 True일 때, True 변환
        - 단축평가
        print(3 and 5) # True and True일 때 True를 출력하므로 `뒤값인 5` 출력

        print(3 and 0) # True and False일 때 False를 출력하므로 `뒤값인 0` 출력

        print(0 and 5) # False and True일 때 False를 출력하므로 `False(0)` 출력

        print(0 and 0) # False and False일 때 False를 출력하므로 `False(0)` 출력
    - `or` : 양쪽 모두 False일 때, False 변환
        - 단축평가
        print(3 or 5) # True or True일 때 True를 출력하므로 `앞값인 3` 출력

        print(3 or 0) # True or False일 때 True를 출력하므로 `앞값인 3` 출력

        print(0 or 5) # False or True일 때 True를 출력하므로 `True인 5` 출력

        print(0 or 0) # False or False일 때 False를 출력하므로 `False(0)` 출력
    - `not` : 반대값 출력

4. 복합연산자
    - `a = a + b` => `a += b`
    - `a = a - b` => `a -= b`
    - `a = a * b` => `a *= b`
    - `a = a / b` => `a /= b`
    - `a = a // b` => `a //= b`
    - `a = a % b` => `a %= b`
    - `a = a ** b` => `a **= b`

5. 기타연산자
    - concatenation : type 통일
        ```python
        a = 'hi'
        b = 'hello'
        a + b => 'hihello'
        ```

    - containment
        ```python
        'a' in 'apple' => `True`
        'z' in 'apple' => `False`
        ```

    - is : 메모리값 위치에 대한 출력
        ```python
        a = 123123
        b = 123123
        `a is b` => `False`

        a = 10
        b = 10
        `a is b` => `True'
        ```
        일정범위에 대한 실수는 True, 그 외에는 False
        (메모리저장 위치가 다르기 떄문)

    - 연산자 우선순위
        0. ()를 통해 그룹
        1. `**`
        2. 산술연산자(`*`, `/`)
        3. 산술연산자(`+`, `-`)
        4. 비교연산자, `is`, `in`
        5. `not`
        6. `and`, `or`

## 3. 형변환
1. 암시적 형변환
    - `True` : 숫자 `1` 취급
    - `False` : 숫자 `0` 취급

2. 명시적 형변환
`a = int`, `b = str`일 때
`str(a) + b`으로 type을 통일시켜줌

    - `input()`으로 입력받을 떄 기본값은 str
    - 2가지 방법으로 `int`로 변환 가능
    ```python
    a = int(input())

    a = input()
    a = int(a)
    ```

    - a = `100` : 1 이상이면 `True`
    - bool('') : 비어있으면 0, 글자가 있으면 1 이상

## 4. 시퀀스 자료형
1. List
    - 선언 : `변수이름 = [value1, value2, value3]`
    - 접근 : `변수이름[index]` ([-1] : 맨 오른쪽에서 첫번째)
2. Tuple
    - 선언 : `변수이름 = (value1, value2, value3)`
    - 접근 : `변수이름[index]`
    - List와 유사하지만 수정불가능(immutable)하다.
3. Range
    - `range(n)` : 0부터 n-1까지 범위
    - `range(n, m)` : n부터 m-1까지 범위
    - `range(n, m, s)` : n부터 m-1까지 범위, +s만큼 증가하는 범위
4. String : 1.4 참고
5. 시퀀스에서 사용가능한 함수
    - `indexing` : `sequence[1]` => 1번째 value 출력
    - `slicing` 
        : `sequence[1:3]` => 1번째 이상 3번째 미만 value 출력

        : `sequence[1:3:2]` => 1번째 이상 3번째 미만 +2씩 value 출력

        : `sequence[:3]` => 0번째 이상 3번째 미만
    - `in` : `1 in sequence` => sequence에 1이 포함된다면 True 출력
    - `not in` : `1 not in sequence` => sequence에 1이 포함되지 않는다면 True 출력
    - `concatentaion` : `sequence + sequence` => sequence 합쳐짐
    - `*` : `sequence * 3` => sequence가 3번 반복
    - `len` : sequence의 value 갯수 출력
    - `min`
    - `max`
    - `count` : `sequence.count(1)` => 1이 몇 개인지 출력

## 5. 시퀀스데이터가 아닌 자료구조
1. set
    - 선언 : `변수이름 = {value1, value2, value3}`

```python
set_a = {1, 2, 3, 4, 5}
set_b = {1, 3, 5, 7, 9}
    - `set - set` : 차집합 => a - b = {2, 4}
    - `set | set` : 합집합 (or) => a | b = {1, 2, 3, 4, 5, 7, 9}
    - `set & set` : 교집합 (and) => a & b = {1, 3, 5}
    - `set(list)` : 중복값 제거
```

2. dictionary
    - 선언 : `변수이름 = {key1: value1, key2: value2, key3: value3}`
    - 접근 : `변수이름[key]`
    - dictionary는 key와 value가 쌍으로 이루어져있다.
    - key에는 immutable한 모든 값 사용가능 (불변값 : string, integer...)
    - value에는 모든 데이터 가능 (list, dict도 가능)

```python
dict_a = {
    'name': 'heeju',
    'age': 10,
    'location': 'busan',
    'numbers': [1, 2, 3, 4, 5],
    'freinds': {
        'a': 10,
        'b': 11,
    },
}

print(dict_a['numbers']) => {1, 2, 3, 4, 5}
print(dict_a['numbers'][3]) => 4
print(dict_a['freinds']['b']) => 11

dict_a.keys() => ['name', 'age', 'location'...]
dict_a.values() => ['heeju', 10, 'busan'...]
```

