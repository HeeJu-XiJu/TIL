# 객체지향 프로그래밍(OOP)

- 클래스(class) : 같은 종류의 집단에 속하는 속성(attribute)과 행위(method)를 **정의**할 것
- 인스턴스(instance) : 클래스를 실제로 메모리상에 할당한 것
- 속성(attribute) : 클래스/인스턴스가 가지고 있는 **데이터**/값
- 행위(method) : 클래스/인스턴스가 가지고 있는 **함수**/기능

## Class
- 클래스 선언
```python
class ClassName:
    attribute = value

    def method_name(self):
        code
```
- 인스턴스화
```python
ClassName()
```

#### class 선언
```python
class MyClass:
    name = 'han'

    def hello(self):
        return 'hello'
```

#### 인스턴스화
```python
a = MyClass()
```

## 생성자, 소멸자
```python
class MyClass:
    def __init__(self):
        pass
    def __del__(self):
        pass
```

##### 예시

```python
class Person:
    name = 'noname'

    def __init__(self, name='익명'):
        self.name = name
        print('생성됨')

    def __del__(self):
        print('소멸됨')
```
```python
p1 = Person('han') # 생성됨
print(p1.name) # han

# 1번 더 실행할 경우
# 생성됨
# 소멸됨 : 기존 생성된 p1이 삭제된 후 다시 생성되므로 소멸됨이 함께 출력
```

##### 연습
```python
# Point
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def info(self):
        return (self.x, self.y)

# Circle
class Circle:

    def __init__(self, point, r):
        self.point = point
        self.r = r

    def info(self):
        return (self.point.x, self.point.y, self.r)

    def move(self, x, y):
        self.point.x = x
        self.point.y = y
```
```python
p1 = Point(3, 3)
print(p1.info()) # (3, 3)

c1 = Circle(p1, 10)
print(c1.point.info()) # (3, 3) Point의 info
print(c1.info()) # (3, 3, 10) Circle의 info
c1.move(5, 5)
print(c1.info()) # (5, 5, 10)
print(p1.info()) # (5, 5)
```

### 클래스 변수
- 클래스 선언 블록 최상단에 위치

### 인스턴스 변수
- 인스턴스 내부에서 생성한 변수('self.variable = ')

```python
class MyClass:
    class_variable = '클래스변수'
    
    def __init__(self, name):
        self.instance_variable = '인스턴스변수'
```

##### 예제
```python
class Person:
    name = '홍길동'
    phone = '010-1234-1234'

    def __init__(self, name):
        self.name = name
```

```python
p1 = Person('한희주')
print(p1.name) # 인스턴스변수 '한희주'
print(Person.name) # 클래스변수 '홍길동'

# print(p1.location) #  p1, Person 모두 location에 대한 데이터가 없으므로 오류
```

## 클래스 메소드, 인스턴스 메소드, 스태틱 메소드
```python
class MyClass:
    def instance_method(self):
        pass
    @classmethod
    def class_method(cls):
        pass
    @staticmethod
    def static_method():
        pass
```

##### 예제
```python
class Puppy:
    num_of_puppy = 0

    def __init__ (self, name):
        self.name = name
        Puppy.num_of_puppy += 1

    @classmethod
    def get_status(cls):
        print(f'현재 강아지는 {cls.num_of_puppy}마리입니다.')

    @staticmethod
    def bark(msg):
        return msg
```

## 상속
```python
class Person:
    def __init__(self, name, email, phone, location):
        self.name = name
        self.email = email
        self.phone = phone
        self.loaction = location

    def greeting(self):
        print(f'안녕하세요. {self.name}입니다.')
```
```python
class Student:
    def __init__(self, name, email, phone, location, student_id):
        self.name = name
        self.email = email
        self.phone = phone
        self.loaction = location
        self.student_id = student_id

    def greeting(self):
        print(f'안녕하세요. {self.name}입니다.')
```

```python
# 아래 주석과 같이 Person정보를 Student에 모두 들고 옴
class Student(Person):
    # def __init__(self, name, email, phone, location):
    #     self.name = name
    #     self.email = email
    #     self.phone = phone
    #     self.loaction = location

    # def greeting(self):
    #     print(f'안녕하세요. {self.name}입니다.')

    # init은 재정의
    def __init__(self, name, email, phone, location, student_id):
        self.name = name
        self.email = email
        self.phone = phone
        self.loaction = location
        self.student_id = student_id

    # super()는 Person(부모클래스) return => 간략화 가능
    def __init__(self, name, email, phone, location, student_id):
    super().__init__(name, email, phone, location)
    self.soldier_id = soldier_id
```

## 다중상속
```python
class Person:
    def __init__(self, name):
        self.name = name

    def breath(self):
        print('후하')
```
```python
class Mom(Person):
    gene = 'xx'

    def swim(self):
        print('어푸어푸')
```
```python
class Dad(Person):
    gene = 'xy'

    def run(self):
        print('다다다')
```
```python
class Baby(Dad, Mom):
    pass
```
```python
b = Baby('금쪽이')
print(b.name) # 금쪽이
print(b.gene) # xy => 상위 클래스의 순서따라 상속받는 데이터가 다름
b.swim() # 어푸어푸
b.run() # 다다다
b.breath() # 후하
```