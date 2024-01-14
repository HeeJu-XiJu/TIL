# Markdown문법

### 1. Headers(헤더)
: 글머리1 ~ 6까지 지원
```
# 제목 1
## 제목 2
### 제목 3
#### 제목 4
##### 제목 5
###### 제목 6
```
# # 제목 1
## ## 제목 2
### ### 제목 3
#### #### 제목 4
##### ##### 제목 5
###### ###### 제목 6


<br>

### 2. BlockQuote(인용문)
```
> 인용문 1
>> 인용문 2
>>> 인용문 3
```

> \> 인용문 1
>> \>> 인용문 2
>>> \>>> 인용문 3


<br>

### 3. List(목록)
#### 3-1 순서가 있는 목록
```
1. 1번째 항목
    1. 하위 항목
2. 2번째 항목
3. 3번째 항목
```

1. 1번째 항목
    1. 하위 항목
2. 2번째 항목
3. 3번째 항목

#### 3-2 순서가 없는 목록
: *, +, - 로 표기(혼합해서 사용 가능)
```
* 항목 1
    * 항목 2
        * 항목 3

* 항목 1
    + 항목 2
        - 항목 3
```

* 항목 1
    * 항목 2
        * 항목 3

* 항목 1
    + 항목 2
        - 항목 3


<br>

### 4. 코드
#### 4-1 코드인용
```
`code`
```

`` `code` ``

#### 4-2 코드블록
: html, css, python, javascript, bash, plaintext 등등
<pre><code>
```python
def func():
        return True
```
</code></pre>

```python
def func():
        return True
```

<br>

<pre><code>
```javascript
console.log('hello')
```
</code></pre>

```javascript
console.log('hello')
```

<br>

<pre><code>
```
code block
```
</code></pre>

```
code block
```


<br>

### 5. 수평선
```
***
---
```

***
---


<br>

### 6. 링크
```
[Title](link)
```

```
[keyword][id]

[id]: link
```

[Google](https://google.com)

[Google][id]

[id]: https://google.com


<br>

### 7. 강조
```
*기울이기*
_기울이기_
**진하게**
__진하게__
~~취소선~~
<u>밑줄</u>
```

*\*기울이기\** \
_\_기울이기\__ \
**\*\*진하게\*\*** \
__\_\_진하게\_\___ \
~~\~\~취소선\~\~~~ \
<u>\<u>밑줄<\/u><u>


<br>

### 8. 줄바꿈
: \  or <br>

```
줄바꾸기전 \
줄바꾸기후
```

줄바꾸기전 \ \
줄바꾸기후

```
줄바꾸기전 <br>
줄바꾸기후
```

줄바꾸기전 \<br> <br>
줄바꾸기후


<br>

### 9. 이미지
#### 9-1 기본문법
```
![대체텍스트](이미지주소)
```

![image](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Google_2015_logo.svg/736px-Google_2015_logo.svg.png)

#### 9-2 링크처리
```
[![대체텍스트](이미지주소)](링크주소)
```

[![image](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Google_2015_logo.svg/736px-Google_2015_logo.svg.png)](https://google.com)

#### 9-3 사이즈조절
```
<img src="이미지주소" width="가로" height="세로"></img>
```

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Google_2015_logo.svg/736px-Google_2015_logo.svg.png" width="100" height=""></img>



<br>

### 10. 표
```
| Header | Header | Header |
| :-- | :--: | --: |
| 왼쪽정렬 | 가운데정렬 | 오른쪽정렬 |
```

| Header | Header | Header |
| :-- | :--: | --: |
| :-- | :--: | --: |
| 왼쪽정렬 | 가운데정렬 | 오른쪽정렬 |