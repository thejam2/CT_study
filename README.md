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
for of문은 반복 가능한 객체의 값을 반복합니다.

Arrays, Strings, Maps, NodeLists 등과 같은 반복 가능한 데이터 구조를 반복할 수 있습니다
```
var iterable = [10, 20, 30];

for (var value of iterable) {
  console.log(value); // 10, 20, 30
}
```

## sort
정렬
```
arr.sort(); //배열의 element들은 문자열로 취급되어, 유니코드 값 순서대로 정렬
arr.sort((a,b)=>a-b);   //숫자 오름차순
arr.sort((a,b)=>b-a);   //숫자 내림차순

```

## ~~
~~ 는 이중 NOT 의 비트 연산자 이다.

양수에 대해서는 Math.floor()과 같고 음수에 대해서는 Math.ceil()과 같은 결과를 나타낸다. 

## reduce
reduce함수는 배열의 각 요소를 순회하며 callback함수의 실행 값을 누적하여 하나의 결과값을 반환 합니다.

다음 4가지의 인수를 가집니다.
1. accumulator - accumulator는 callback함수의 반환값을 누적합니다.
2. currentValue - 배열의 현재 요소
3. index(Optional) - 배열의 현재 요소의 인덱스
4. array(Optional) - 호출한 배열

```
arr.reduce((accumulator, currentValue, index, array)=>{
}, 초기값(option));
```

## filter
