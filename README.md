# CT_study


## for
### for …in 반복문
for in 반복문은 객체의 속성들을 반복하여 작업을 수행할 수 있습니다.

모든 객체에서 사용이 가능합니다.

for in 구문은 객체의 key 값에 접근할 수 있지만, value 값에 접근하는 방법은 제공하지 않습니다.

자바스크립트에서 객체 속성들은 내부적으로 사용하는 숨겨진 속성들을 가지고 있습니다. 

그중 하나가 [[Enumerable]]이며, for in 구문은 이 값이 true로 셋팅되어 속성들만 반복할 수 있습니다.

이러한 속성들을 열거형 속성이라고 부르며, 객체의 모든 내장 메서드를 비롯해 각종 내장 프로퍼티 같은 비열거형 속성은 반복되지 않습니다.
```
var obj = {
    a: 1, 
    b: 2, 
    c: 3
};

for (var prop in obj) {
    console.log(prop, obj[prop]); // a 1, b 2, c 3
}
```
### for …of 반복문
for of 반복문은 ES6에 추가된 새로운 컬렉션 전용 반복 구문입니다.

for of 구문을 사용하기 위해선 컬렉션 객체가 [Symbol.iterator] 속성을 가지고 있어야만 합니다(직접 명시 가능).
```
var iterable = [10, 20, 30];

for (var value of iterable) {
  console.log(value); // 10, 20, 30
}
```

## ~~
~~ 는 이중 NOT 의 비트 연산자 이다.

양수에 대해서는 Math.floor()과 같고 음수에 대해서는 Math.ceil()과 같은 결과를 나타낸다. 

