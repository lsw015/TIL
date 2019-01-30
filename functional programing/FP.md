# 함수형 프로그래밍

## 함수형 프로그래밍 이란?

- 자료 처리를 수학적 함수의 계산으로 취급하고 상태와 가변 데이터를 멀리하는 프로그래밍 패러다임의 하나이다
- 함수를 값처럼 여기며 순수 함수(pure function)를 조합하고 가변 데이터(mutable data) 및 부작용(side-effects) 을 피하는 프로그래밍 패러다임이다.

## 함수형 프로그래밍 규칙

- 모든 데이터는 변경이 불가능(Immutable) 해야한다.
- 모든 함수는 순수 함수이여야 한다.
- 루프보다는 재귀를 사용한다.

## 1급 객체

다음과 같은 조건을 만족하는 객체

> - 변수나 데이터 구조안에 담을 수 있다.
> - 파라미터로 전달 할 수 있다.
> - 반환값(return value)으로 사용할 수 있다.
> - 할당에 사용된 이름과 관계없이 고유한 구별이 가능하다.
> - 동적으로 프로퍼티 할당이 가능하다.

Javascript에서 함수는 1급 객체이다.

## 불변성

> - 함수형 프로그래밍에서는 데이터가 변할 수 없다
> - 데이터 변경이 필요한 경우, 원본 데이터 구조를 변경하지 않고 그 데이터를 복사본을 만들어 그 일부를 변경하고, 변경한 복사본을 return 한다

```javascript
// Mutatable
function changeRanking(user, ranking) {
  user.ranking = ranking
  return user
}
const smith = { ranking: 10, name: 'smith' }
changeRanking(smith, 5)
console.log(smith.ranking) // 5

// Immutable
function changeRanking(user, ranking) {
  return { ...user, ranking }
}
const john = { ranking: 2, name: 'john' }
const changedJohn = changeRanking(john, 1)
console.log(john.ranking) // 2 변하지 않음
console.log(changedJohn.ranking) // 1
```

## 순수 함수

> - 동일한 입력에는 항상 같은 값을 반환해야 한다.
> - 함수의 실행은 프로그램의 실행에 영향(외부 변수 수정, 삭제, 추가 등...)을 미치지 않아야 한다. (Side effect 가 없어야 한다)

```javascript
// 비 순수함수(c의 값에 따라 다른 값이 반환됨)
function sum(a, b) {
  return a + b + c
}
// 비 순수함수(sum이라는 외부 변수의 값을 수정함)
function sum2(a, b) {
  sum = a + b
  return a + b
}

// 순수함수
function sum3(a, b) {
  return a + b
}
```

## 고차 함수

> - 함수에 함수를 파라미터로 전달하는 함수
> - 반환값으로 함수를 반환하는 함수

Array.prototype의 map, filter, forEach등 다 고차 함수이다.

## 커링(currying)

- 커링이란 여러개의 파라미터를 가진 함수를 호출 할 경우, 파라미터의 수보다 적은 수의 파라미터를 인자로 받으면 누락된 파라미터를 다음 파라미터로 받는 기법

```javascript
function sum(a, b) {
  return a + b
}

// bind를 사용한 currying
const addOne = sum.bind(null, 1)
console.log(addOne(10)) // 11

// 직접 커링 구현
function curry(fn, ...args) {
  // 첫번째 인자가 함수가 아닐때
  if (typeof fn !== 'function') {
    console.error('첫번째 인자로 함수를 넣어주세요')
    return
  }
  // 2번째 이후 인자로 받은 인자수가 첫번째 인자로 받은 함수의 인자수보다 크거나 같을때
  if (args.length >= fn.length) {
    return fn(...args)
  }
  // 2번째 이후 인자로 받은 인자수가 첫번째 인자로 받은 함수의 인자수보다 적을때 재귀호출
  return (...more) => curry(fn, ...args, ...more)
}
const addOne2 = curry(sum, 1)
console.log(addOne2(1)) // 2
```

## 합성 함수

- 합성 함수란 새로운 함수를 만들어거나 계산하기 위해 둘 이상의 함수를 조합하는 과정을 말한다. 함수형 프로그래밍은 함수를 값으로 여길수 있기 때문에 함수들을 연쇄적으로 호출하여 더 큰 함수를 만들수 있다.

```javascript
function sum(a, b) {
  return a + b
}
const addTwo = sum.bind(null, 2) // 함수 커링
console.log(addTwo(sum(2, 6))) // 10
```

## 지연평가 & 메모이제이션

TODO