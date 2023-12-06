# 😰 1. 자바스크립트의 한계

&#x20;1\. 동적 타입 언어

자바스크립트는 변수가 할당 되는 시점에 타입이 정해진다.



2. 동적 타이핑 시스템의 한계

<pre class="language-javascript"><code class="lang-javascript">// 숫자(number) a + b 를 반환하는 함수
<strong>const setNumber (a,b) => {
</strong>    return a + b;
}

setNumber(1,2); // 3
</code></pre>

위의 코드를 실행하면 정상적으로 출력된다.&#x20;

만약에 두개의 인자를 받는 setNumber 함수에 a만 전달하면 어떤 상황이 일어날까?

```javascript
// 인자 a만 전달
const setNumber (a,b) => {
    return a + b;
}

setNumber(1); // NaN
```

이 코드는 문제없이 동작한다.

이유는 자바스크립트 엔진에서 찾아볼 수있다.

자바스크립트는 setNumber함수가 실행 될 때 즉 런타임에 사용되는 인자 값에 따라 타입이 결정된다.

a는 Number 타입이 전달 되었고 b는 undefined 로 형 변환이 일어나서 1 + undefind = NaN 이 출력 된 것 이다.



따라서 기계 입장에서는 정상적이지만 사람 입장에서는 정상적이지 않은 코드이다.

개발자들이 코드를 작성하는 시점이 아닌 프로덕션에 올라가서 유저가 사용을 하다가 에러를 마주칠 수 있어서 안전하지 않다
