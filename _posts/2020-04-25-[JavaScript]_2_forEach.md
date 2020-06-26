# JavaScript Array forEach

JavaScript `Array` 에서 사용하는 `for`문이라고 생각하면 쉽다. 하지만 우리가 알고 있는 일반적인 `for`문 처럼 초기화,조건문,증감식 등이 필요없다.  
`forEach`문은 `Array`내 모든 요소들을 확인하고 그요소에 대하여 반복문을 진행한다. `for`문 처럼 break,continue,break처럼 반복문을 중도에 멈출 수 없고 throw을 활용하여 예외처리를 해야한다.

### 간단한 forEach문 예제와 설명

```javascript
var int_Array = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

int_Array.forEach((a) => {
  if (a % 2 == 1) {
    console.log(int_Array[a]);
  }
});
```

int_Array안에 있는 요소에 대하여 `for`문을 돌린다.`a`를 int_Array[]의 index 값이라고 생각하면 쉽다. 결국 이 `forEach`문은 int_Array[0]~int_Array[9]까지의 `for`문이다.  
`a%2==1`은 index가 홀 수 일때만 `if`문을 실행한다.
만약 이 코드를 for문으로 작성한다면

```javascript
var int_Array = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
for (var i = 0; i < int_Array.length; i++) {
  if (i % 2 == 1) {
    console.log(int_Array[i]);
  }
}
```

확실히 Array에 대한 전체적인 `for`문을 돌린다면 forEach문이 훨씬 경제적으로 보인다.`i`값의 초기화,조건문,증감식이 없기때문에 코드가 훨씬더 보기편하고 경제적이다.
