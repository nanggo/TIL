# 화살표 함수에서의 객체 리턴
화살표 함수에 대해서 객체를 리턴할 경우 아래와 같이 중괄호를 소괄호로 감싸줌으로써 리턴하는 값이 객체임을 표현할 수 있다.

### 일반적인 함수

```javascript
var add = function(a, b) {
  return { val: a + b }
}
```

### 화살표 함수

```javascript
var add = (a, b) => ({ val: a + b })
```