
![header](https://capsule-render.vercel.app/api?type=waving&color=timeGradient&height=300&section=header&fontSize=35&text=Clean%20Code&animation=fadeIn&fontAlignY=42&fontAlign=16)

<br/>

---

## 목차

- [Ch01. Getting Started](#ch01-getting-started) <br/>


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

#

### 04. 왜 의미있는 Naming 이 중요한가요?

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

### 05. Variables & Constants 는 어떻게 네이밍하는 것이 좋을까요?

```Javascript
const userData = {...}
const isValid = true
```

- Variables & Constants는 주로 입력값이나, 결과등 데이터 컨테이너입니다.
- 이러한 Variables & Constants에는 **명사형**으로 써주거나 형용사를 사용한 짧은 phrases로 네이밍합니다.

#

### 06. Function / Methods 는 어떻게 네이밍하는 것이 좋을까요?

```python
sendData()
inputIsValid()
```

- Function / Methods는 data를 서버에 보내라 같은 특정 명령이나 인풋값을 bool로 검증하기 등 value를 계산합니다.
- 이러한 unction / Methods 주로 **동사형**을 써주거나 형용사를 사용한 짧은 phrases로 네이밍합니다.

#

### 07. Class는 어떻게 네이밍하는 것이 좋을까요?

```python
class User { ... }
class RequestBody { ... } //combination nouns
```
- class는 주로 user, product, http request body 등 things를 만들 때 사용합니다
- Class는 **명사형**으로 네이밍합니다

#

### 08. variabe을 네이밍할 때 타입에 따라 어떻게 네이밍하면 좋을까요?

- 변수나 속성의 타입이 object, number or string이라면 내용물을 명사로 적어줍니다 (ex. user, database, name, age)
- 만약 좀더 디테일한 정보를 담고 싶다면 명사형을 조합해줍니다(ex. authenticatedUser, sqlDatabase, firstName, age)
- 변수나 속성의 타입이 bool이라면 네이밍에 대한 답이 true/false가 되야합니다(ex. isActive, loggenIn)

#

### 09. variabe을 네이밍할 때 주의해야할 점이 어떤 것이 있을까요?

- Variable에 어떤 데이터를 저장했는지 specific하게 담겨야합니다
- 그냥 `you`, `data`는 너무 광범위합니다. 대신에 `userData`, `person`과 같이 내용물을 Specific하게 네이밍해주어야 합니다.
- 하지만 `userData`, `person` 는 redundant하거나 불분명합니다. 대신에 `user`, `customer`로 네이밍해주는 것이 좋습니다.
- Bool타입을 네이밍할경우 descriptive하게 적어줌으로서 Bool타입이라는 것을 네이밍을 통해 알려주는 것이 좋습니다
- 예를들어 단순히 `correct`, `validatedInput`보다는 `isCorrect`, `isValid`라고 적어주는 것이 좋습니다.

#

### 10. Functinos & method를 네이밍할 때 주의해야할 점이 어떤 것이 있을까요?

- function에는 작업을 동사형으로 묘사해줍니다 -> `getUser(...)`, `response.send()`
- 이때 Boolen을 계산하는 function에는 descriptive하게 네이밍합니다 -> `isValid(...)`, `purchase.isPaid()`





