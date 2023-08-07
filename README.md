
![header](https://capsule-render.vercel.app/api?type=waving&color=timeGradient&height=300&section=header&fontSize=35&text=Clean%20Code&animation=fadeIn&fontAlignY=42&fontAlign=16)

<br/>

---

## 목차

- [Ch01. Getting Started](#ch01-getting-started) <br/>


<br/>

---

## Ch01. Getting Started

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
