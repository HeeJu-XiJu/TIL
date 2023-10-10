# Datastructure

## 문자열 메소드
```python
a = 'hello my name is heeju'
a[0] = 'H' 
# error 발생 => String은 immutable
```

```python
.capitalize() # 첫글자 대문자
.title() # 단어 첫글자 대문자
.upper() # 문장 전체 대문자
.lower() # 문장 전체 소문자
```

#### .strip
```python
.strip([chars]) # 왼쪽 오른쪽의 문자 제거

print(my_string2.strip('hi')) # ello
print(my_string2.lstrip('hi')) # ellohihihi
print(my_string2.rstrip('hi')) # hihihihihello
```


#### .replace
```python
.replace(old, new[, count])

'wooooooow'.replace('o', '!', 3) # 'w!!!oooow'
```

#### .find
```python
.find(x)

'apple'.find('a') # 0
'apple'.find('z') # 없을 경우 -1 출력
```

#### .index
```python
.index(x)
'apple'.index('a') # 0
'apple'.index('z') # error
```

#### .split
```python
.split(x)
'my_name_is'.split('_') # ['my', 'name', 'is']
```

#### .count
```python
.count(x)
'wooooow'.count('o') # 5
```

## 리스트 메소드

#### .append
```python
.append()
numbers = [1, 5, 2, 6, 2, 1]
numbers.append(10) # [1, 5, 2, 6, 2, 1, 10]
```

#### .extend
```python
.extend(iterable)
numbers.extend([99, 100]) # [1, 5, 2, 6, 2, 1, 10, 99, 100]
```

#### .insert
```python
.insert(idx, x)
numbers.insert(3, 3.5) # [1, 5, 3.5, 6, 2, 1, 10, 99, 100]
```

#### .remove
```python
.remove(x)
numbers.remove(3.5) # [1, 5, 2, 6, 2, 1, 10, 99, 100]
```

#### .pop
```python
.pop()
numbers.pop() # [1, 5, 2, 6, 2, 1, 10, 99]
```

#### .sort
```python
.sort() # 원본 수정
numbers.sort() # [1, 1, 2, 2, 5, 6, 10, 99]
numbers.sort(reverse=True) # [99, 10, 6, 5, 2, 2, 1, 1]
```

#### sorted
```python
sorted() # 원본 복원
sorted(numbers) # [1, 1, 2, 2, 5, 6, 10, 99]
# print할 경우 [1, 5, 2, 6, 2, 1, 10, 99]
```

#### .reverse
```python
.reverse()
numbers.reverse() # [99, 10, 1, 2, 6, 2, 5, 1]

numbers[ : : -1] # 동일값
```

### list copy
```python
origin_list = [1, 2, 3]
copy_list = origin_list

copy_list[0] = 100

print(origin_list) # [100, 2, 3]
print(copy_list) # [100, 2, 3]

# list가 새로 만들어진 것이 아닌 list가 저장된 위치를 출력하는 개념
```

```python
# 해결방안
origin_list = [1, 2, 3]
copy_list = list(origin_list)
or copy_list = origin_list[ : ]

copy_list[0] = 100

print(origin_list) # 1, 2, 3]
print(copy_list) # [100, 2, 3]
```

```python
origin_list = [1, 2, [99, 100]]
copy_list = origin_list[ : ]
copy_list[2][1] = 1000 # 2번째 리스트 안에 1번째 값을 수정

print(origin_list) # [1, 2, [99, 1000]]
print(copy_list) # [1, 2, [99, 1000]]
```

```python
# 해결방안
import copy
origin_list = [1, 2, [99, 100]]
copy_list = copy.deepcopy(origin_list)
copy_list[2][1] = 1000

print(origin_list) # [1, 2, [99, 100]]
print(copy_list) # [1, 2, [99, 1000]]
```

### list comprehension
```python
result = []

for number in numbers:
    result.append(number ** 3)
```

```python
 result2 = [number ** 3 for number in numbers]
```

## 딕셔너리 메소드
```python
info = {
    'name' : 'heeju',
    'location' : 'busan',
}
```

```python
info['name'] = 'han' # {'name': 'han', 'location': 'busan'}
```

#### .pop
```python
.pop(key[, default])
info.pop('location') # {'name': 'han'}
info.pop('location', 'key가 없습니다.') # 지워질 키워드가 없을 때 default값 출력
```

#### .update
```python
.update(key=value)
info.update(name='park') # {'name': 'park'}
```

#### .get
```python
.get(key[, default])
info.get('name') # park
info.get('phone') # none
info.get('phone', '해당 키가 없습니다.') # 해당 키가 없습니다.
```

### dict comprehension
```python
result = {}
numbers = range(1, 11)
for number in numbers:
    result[number] = number ** 3
```

```python
result = {number: number ** 3 for number in range(1, 11) }
```

## 세트 메소드
#### .add
```python
.add(x)
fruits = {'apple', 'banana', 'melon'}
fruits.add('watermelon') # {'apple', 'banana', 'melon', 'watermelon'}
fruits.add('watermelon') # 반복명령해도 중복값은 출력되지 않음 {'apple', 'banana', 'melon', 'watermelon'}
```

#### .update
```python
.update()
fruits.update('grape') # {'apple', 'banana', 'e', 'a', 'r', 'watermelon', 'p', 'melon', 'g'}
fruits.update({'grape', 'orange'}) # {'apple', 'melon', 'banana', 'grape', 'orange'}

# add는 1가지 정보, update는 여러가지 정보를 추가할 때 사용
```

#### .remove
```python
.remove(x)
fruits.remove('orange') # {'apple', 'melon', 'banana', 'grape'}
```

#### .pop
```python
.pop()
fruits.pop() # {'melon', 'banana', 'grape'}
# 랜덤으로 제거
```

### map, filter, zip

#### map(function, iterable)
```python
a = [1, 2, 3]
number_str = map(str, a)
print(number_str) # <map object at 0x111f4e2c0>
print(list(number_str)) # ['1', '2', '3']
```

#### filter(function, iterable)
filter에 들어가는 function은 T/F를 반환해야 함
```python
def is_odd(x):
    return bool(x % 2)

numbers = [1, 2, 3, 4, 5]
result = filter(is_odd, numbers)
print(list(result)) # [1, 3, 5]
```

#### zip
```python
a = [1, 2, 3]
b = [100, 200, 300, 400] # index가 다를 때 작은 index만큼 출력

result = zip(a, b)
print(result) # <zip object at 0x11248d600>
print(list(result)) # [(1, 100), (2, 200), (3, 300)]
```