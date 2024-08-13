Promise / async, await
=============
(Javascript 비동기 작업)

### #Promise 객체
* 사용법:
<pre>
  <code>
    const pr = new Promise((resolve, reject) => {
      //code
    });
  </code>
</pre>
* 상태:
  - 대기(Pending): 비동기 함수 실행 전 -> undefined
  - 성공(Fulfilled): 비동기 함수 성공적으로 이행 -> value
  - 실패(Rejected): 비동기 함수 실패 -> error

* 상태 처리:
  - then(): resolve일 때 실행
  - catch(): reject일 때 실행
  - finally(): 성공이던 실패던 무조건 실행

#### **Promise.all()** (프로미스 체이닝)
: 연속된 여러개의 함수를 콜백함수로 중첩하기 보다 Promise.all()을 쓰면 시간절약 가능하다.
<pre><code>Promise.all( [f1(), f2(), f3()] ).then((res) => {});</code></pre>
> 해석: function 1,2,3 이 모두 실행되어야 then이 실행된다.

#### **Promise.race()**
<pre><code>Promise.race( [f1(), f2(), f3()] ).then((res) => {});</code></pre>
> 해석: function 하나라도 성공 이행되면 then이 실행된다.

<br />

### #async & await
: Promise를 반환하는 키워드 (이 안의 함수는 비동기 함수임을 명시한다)
- promise의 then을 여러번 쓸 필요 없고, try/catch 를 사용하여 비동기코드의 성공, 에러 여부를 확인할 수 있다.
- resolve의 결과를 try에 넣고, reject error의 결과 코드를 catch에 넣어 사용할 수 있다.  

<pre>
  <code>
    async function handleSomething() {
      //code
      return doneFnc;
    });
  </code>
</pre>
> 해석: return Promise.resolve(doneFnc) 와 같은 결과를 가져온다.
<pre>
  <code>
    async function handleSomething() {
      const data = await some.requestData({
        //code
      });
      return data
    }
  </code>
</pre>
> 해석: some의 값이 변경되길 기다렸다 변경되면 그 값을 data에 넣고 data를 반환하는 비동기 함수 handleSomething()를 정의한 것
