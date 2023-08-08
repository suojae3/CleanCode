
![header](https://capsule-render.vercel.app/api?type=waving&color=timeGradient&height=300&section=header&fontSize=35&text=Clean%20Code&animation=fadeIn&fontAlignY=42&fontAlign=16)

<br/>

---

## 목차

- [Ch01. Getting Started](#ch01-getting-started) <br/>
- [Ch02. Naming](#ch02-naming) <br/>


<br/>

---

## Ch01. Getting Started

<br/>

### 01. 가독성을 위해 모든 변수에 type 명을 표기해야하나요?

```python
//types
function add(num1: number, num2: number) {
  retrun num1 + num2;
}

//without types
def add(num1, num2):
  return num1 + num2
```
- 그렇지 않습니다. clean code는 Strong typing 을 필요로 하지 않습니다
- 타입을 써주는 이유는 가독성도 있지만 주된 이유는 에러를 피하기 위해서입니다
- 클린 코드로 적으면 타입을 적어주지 않더라도 가독성과 에러 회피 두 마리 토끼를 잡으면서도 간결하게 코드 작성이 가능해집니다

#

### 02. Clean Code 에서는 아키텍쳐를 다루는 것인가요?

&nbsp;&nbsp;&nbsp;&nbsp;<img src="image/1.png" width="400" height="200"><br/>

- 클린 코드와 클린 아키텍쳐는 다른 범위입니다
- 클린 코드는 **어떻게(How)** 작성하는지 포커스를 둡니다. 
- 클린 아키텍쳐는 code를 **어디에(Where)** 작성하는지 포커스를 둡니다

#

### 03. 왜 클린코드를 작성해야하나요?

&nbsp;&nbsp;&nbsp;&nbsp;<img src="image/2.png" width="400" height="200"><br/>

- Dirty code를 작성하면 빠르게 작성할 수는 있습니다
- 하지만 나중에 유지보수나 버그를 잡는 순간이 오게되면 시간이 훨씬 더 많이 걸리게 됩니다.
- 반면 클린코드를 작성하면 초반에는 시간이 걸릴 수 있으나 나중에가서는 버그를 잡거나 유지보수함에 있어 오히려 시간을 절약하게 됩니다

<br>

--- 

## Ch02. Naming

<br/>

### 01. 왜 의미있는 Naming 이 중요한가요?

```python
//bad exmaple
const us = new MainEntity();
us.process();

if (login) {
  //...
}

//Meangingful Naming
const user = new User();
user.save();

if (isLoggedIn) {
  //...
}
```
- Naming이 Meaningful하면 내용물을 굳이 들여다보지않더라도 의미를 짐작할 수 있습니다
- 읽는사람으로 하여금 코드에 대한 이해도를 빠른시간에 높일 수 있습니다

#

### 02. Variables & Constants 는 어떻게 네이밍하는 것이 좋을까요?

```Javascript
const userData = {...}
const isValid = true
```

- Variables & Constants는 주로 입력값이나, 결과등 데이터 컨테이너입니다.
- 이러한 Variables & Constants에는 **명사형**으로 써주거나 형용사를 사용한 짧은 phrases로 네이밍합니다.

#

### 03. Function / Methods 는 어떻게 네이밍하는 것이 좋을까요?

```python
sendData()
inputIsValid()
```

- Function / Methods는 data를 서버에 보내라 같은 특정 명령이나 인풋값을 bool로 검증하기 등 value를 계산합니다.
- 이러한 unction / Methods 주로 **동사형**을 써주거나 형용사를 사용한 짧은 phrases로 네이밍합니다.

#

### 04. Class는 어떻게 네이밍하는 것이 좋을까요?

```python
class User { ... }
class RequestBody { ... } //combination nouns
```
- class는 주로 user, product, http request body 등 things를 만들 때 사용합니다
- Class는 **명사형**으로 네이밍합니다

#

### 05. variabe을 네이밍할 때 타입에 따라 어떻게 네이밍하면 좋을까요?

- 변수나 속성의 타입이 object, number or string이라면 내용물을 명사로 적어줍니다 (ex. user, database, name, age)
- 만약 좀더 디테일한 정보를 담고 싶다면 명사형을 조합해줍니다(ex. authenticatedUser, sqlDatabase, firstName, age)
- 변수나 속성의 타입이 bool이라면 네이밍에 대한 답이 true/false가 되야합니다(ex. isActive, loggenIn)

#

### 06. variabe을 네이밍할 때 주의해야할 점이 어떤 것이 있을까요?

- Variable에 어떤 데이터를 저장했는지 specific하게 담겨야합니다
- 그냥 `you`, `data`는 너무 광범위합니다. 대신에 `userData`, `person`과 같이 내용물을 Specific하게 네이밍해주어야 합니다.
- 하지만 `userData`, `person` 는 redundant하거나 불분명합니다. 대신에 `user`, `customer`로 네이밍해주는 것이 좋습니다.
- Bool타입을 네이밍할경우 descriptive하게 적어줌으로서 Bool타입이라는 것을 네이밍을 통해 알려주는 것이 좋습니다
- 예를들어 단순히 `correct`, `validatedInput`보다는 `isCorrect`, `isValid`라고 적어주는 것이 좋습니다.

#

### 07. Functinos & method를 네이밍할 때 주의해야할 점이 어떤 것이 있을까요?

- function에는 작업을 동사형으로 묘사해줍니다 -> `getUser(...)`, `response.send()`
- 이때 Boolen을 계산하는 function에는 descriptive하게 네이밍합니다 -> `isValid(...)`, `purchase.isPaid()`
- 좋은 네이밍을 할 때는 질문하는 것이 좋습니다. 무엇을 process하는거지? 무엇을 save하는거지? 무얼 의도하는거지 (ex. `process()` -> `save()` -> `saveUser()`) 

#

### 08. Class를 네이밍할 때 주의할 점은 어떤 것이 있을까요?

&nbsp;&nbsp;&nbsp;&nbsp;<img src="image/3.png" width="400" height="200"><br/>

- Class는 중복되는 정보가 있으면 안됩니다
- 예를들어 `class UserOBJ` 대신에 `class User`로 이름짓는 것이 좋습니다
- 또한 클래스 내에 메서드들이 서로 distinctive 해야합니다. 사진과 같이 무논리로 나열해버리면 나중에 버그찾기가 매우 힘들어집니다

#

### 09. 네이밍할 때 일관성을 지켜야한다는 것이 어떤 뜻인가요?

```python
database = Database()

database.get_users()

database.get_products() //in line with get_users()

database.fetch_products() // ??? what the..?
```

- 전체적인 프로그램에서 네이밍함에 있어 일정한 네이밍 규칙을 적용해야합니다
- 예를들어 `get`을 썼으면 일관되게 `get`을 적용하게 `fetch`는 지양합니다

#

### 10. 아래 읽기 힘든 `BlogPost()` 클래스의 네이밍을 다시해주세요

```python
class BlogPost:
  def __init__(self, title, description, ymdhm):
    self.title = title
    self.description = description
    self.ymdhm = ymdhm

  def output(item):
    print('Title: ' + item.title)
    print('Description: ' + item.description)
    print('Published: ' + item.ymdhm)

summary = 'Clean Code Is Great'
desc = 'Actually, writing Clean code can be pretty fun.'
new_date = datetime.now()
publish = new_date.strftime('%Y-%m-%d %H:%M')

item = BlogPost(summary, desc, publish)

output(item)
```

- `ymdhm`(년월일시간분)같은 축약어는 알아보기 힘들기 때문에 `date`로 바꿔줍니다. 하지만 어떤 `date`인데? 라는 물음에 답하기 위해 `date_published`로 구체화해줍니다.
- `output()`은 그래서 어떤 output인지에 대해 불명확하므로 `print_blog_post()`처럼 구체화해줍니다. 이를 통해 아 얘는 블로그 포스트를 프린트하는 함수구나를 쉽게 알 수 있습니다.
- `item`대신에 구체적으로 `blog_post`로 바꾸어준뒤 같은 범위내 네이밍의 통일성을 부여해줍니다. `item.title` -> `blog_post.title`, `item.description` -> `blog_post.description`, `item.ymdhm` -> `blog_post.date_published`
- `summary`에 담긴 내용물은 제목이기 때문에 `title`로 바꿔줍니다
- `desc`같은 축약어는 지양합니다 `decription`으로 바꿔줍니다.
- `new_today`처럼 애매모호한 네이밍보다는 `now`와 같은 직관적인 네이밍으로 바꿔줍니다
- `publish`는 동사형이기 때문에 명령문처럼 보입니다. 이는 변수 네이밍의 나쁜예로 data container의 특성을 살려주는 명사형으로 `formatted_date`로 바꿔줍니다.
- 이를 적용해서 네이밍을 다시한 코드는 아래와 같습니다
  
```python
class BlogPost:
  def __init__(self, title, description, date_published):
    self.title = title
    self.description = description
    self.date_published = date_published

  def print_blog_post(blog_post):
    print('Title: ' + blog_post.title)
    print('Description: ' + blog_post.description)
    print('Published: ' + blog_post.date_published)

title = 'Clean Code Is Great'
description = 'Actually, writing Clean code can be pretty fun.'
now = datetime.now()
formatted_date = now.strftime('%Y-%m-%d %H:%M')

blog_post = BlogPost(summary, description, formatted_date)

print_blog_post(blog_post)
```


























