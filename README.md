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
filter() 메서드는 주어진 함수의 테스트를 통과하는 모든 요소를 모아 새로운 배열로 반환
```
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);

console.log(result);
// Expected output: Array ["exuberant", "destruction", "present"]
```


### 최대공약수, 최소공배수
```
// 최대공약수
function gcd(minNum, maxNum){
  return (minNum % maxNum) === 0 ? maxNum : gcd(maxNum, minNum % maxNum);
}
// 최소공배수
function lcm(minNum, maxNum){
  return minNum * maxNum / gcd(minNum, maxNum);
}
```

### pop(array)
pop()
배열에서 마지막 요소를 제거하고 그 요소를 반환한다.

### shift(array)
shift()
배열에서 첫 번째 요소를 제거하고, 제거된 요소를 반환한다.
이 메서드는 배열의 길이를 변하게 한다.

### ??(널리쉬 연산자)
a ?? b의 결과는 다음과 같습니다.
a가 null도 아니고 undefined도 아니면 a
그 외의 경우는 b


### Array.from()
Array.from 은 유사 배열 객체를 배열로 바꾼다.
```
Array.from('Tei');
//["T", "e", "i"]
```

### Array.join()
배열에 있는 원소들을 하나의 값으로 만듭니다.

원소들의 구분은 콤마(,)로 합니다.

원소들의 구분을 다른 문자로 하려면 () 안에 원하는 문자를 넣습니다.
```
const arr = ['바람', '비', '물'];

console.log(arr.join());
// 바람,비,물
console.log(arr.join(''));
// 바람비물
console.log(arr.join('-'));
// 바람-비-물
```

### Array.reverse()
reverse() 메서드는 배열의 순서를 반전합니다. 원본을 수정합니다.
```
const array1 = ['one', 'two', 'three'];
console.log('array1:', array1);
// Expected output: "array1:" Array ["one", "two", "three"]

const reversed = array1.reverse();
console.log('reversed:', reversed);
// Expected output: "reversed:" Array ["three", "two", "one"]

// Careful: reverse is destructive -- it changes the original array.
console.log('array1:', array1);
// Expected output: "array1:" Array ["three", "two", "one"]
```

### indexOf
indexOf() 메서드는 호출한 String 객체에서 주어진 값과 일치하는 첫 번째 인덱스를 반환합니다. 일치하는 값이 없으면 -1을 반환합니다.

### Array.some()
some() 메서드는 배열 안의 어떤 요소라도 주어진 판별 함수를 적어도 하나라도 통과하는지 테스트합니다.

만약 배열에서 주어진 함수가 true을 반환하면 true를 반환합니다. 그렇지 않으면 false를 반환합니다.

이 메서드는 배열을 변경하지 않습니다.
```
const array = [1, 2, 3, 4, 5];

// Checks whether an element is even
const even = (element) => element % 2 === 0;

console.log(array.some(even));
// Expected output: true
```

### Array.every()
every() 메서드는 배열 안의 모든 요소가 주어진 판별 함수를 통과하는지 테스트합니다.

Boolean 값을 반환합니다.
```
const isBelowThreshold = (currentValue) => currentValue < 40;

const array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// Expected output: true
```

### Array.includes()
배열이 특정 요소를 포함하고 있는지 판별
```
const array1 = [1, 2, 3];

console.log(array1.includes(2));
// Expected output: true

const pets = ['cat', 'dog', 'bat'];

console.log(pets.includes('cat'));
// Expected output: true

console.log(pets.includes('at'));
// Expected output: false

```
