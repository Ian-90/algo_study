## Big O Notation
### 1. 정의
* 문제를 해결할 떄, 어느 것(코드)이 더 좋은지 성능을 비교하고 평가하는 것

### 2. Example
* 1 ~ N 까지의 합
  ```js
  function addUpToFirst(n) {
    let total = 0;
    for (let i = 1; i <= n; i++) {
      total += i;
    }
    return total
  }

  function addUpToSecond(n) {
    return n * (n + 1) / 2;
  }

  // 측정 방법
  let t1 = performance.now()
  addUpToFirst(1000000)
  let t2 = performance.now()
  console.log(`Time Elapsed: ${(t2 - t1) / 1000} seconds.`)
  ```

### 3. 측정 방법
* 코드를 비교할 떄 시간을 사용하면 조금씩 차이가 나기 때문에 문제가 있다. 그렇기 때문에 컴퓨터가 처리하는 연산의 개수를 세는 것이 좋다. 어떤 컴퓨터를 사용하더라도 연산은 변하지 않기 때문이다.
* 연산 개수
  * addUpToFirst - 5n + 2
    * `let total 1 = 0` - 1번
    * `for문의 i++` - n번(+ 연산자) + n번(= 연산자)
    * `total += i` - n번 + n번
    * `i = 1` - 1번
    * `i <= n` - n번
  * addUpToSecond- 3
    * `+, *, /` - 3번

### 4. Big O
* 입력된 내용이 늘어날 수록 알고리즘에 실행 시간이 어떻게 변하는지 설명하는 공식적인 방식
* 입력의 크기와 실행시간의 관계
* Big O를 쉽게 판단 하는 규칙
  * 상수
    1. 산수(사칙 연산)
    2. 변수 배정
    3. 배열의 인덱스나 객체의 키로 데이터에 접근하는 것
  * n
    * 루프

* ex
  * addUpToFirst - O(1)
  * addUpToSecond - O(n)

### 5. 공간 복잡도(space complexity)
* 시간 복잡도(time complexity) - 알고리즘들이 얼마나 빠르게 실행하는지, 입력이 커질수록 알고리즘의 실행 속도가 어떻게 바뀌는지

* 공간 복잡도(space complexity) - 입력이 커질수록 알고리즘이 얼마나 많은 공간을 차지 하는지
  * boolean, number, undefined, null은 js에서 불변 공간
  * string은 O(n)의 공간
  * reference type(array, object..)은 O(n)의 공간

### 6. Logarithm Complexity
* O(1) < O(logn) < O(n) < O(nlogn) < O(n^2)
