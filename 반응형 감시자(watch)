 반응형 감시자
=============
* Composition API

### watch()
* 사용법:
-  import { watch } from "vue";
-  상태 변경에 대한 반응을 보여줘야 할 때(DOM 변경, 비동기 작업의 결과 등) 사용한다
-  반응형 객체, 함수, 배열 등 인자에 다양하게 사용할 수 있으나, **반응형 속성은 사용할 수 없으므로 getter함수를 대신하여 사용**한다.
<pre>
  <code>
    <script setup>
    const x = ref(0)
    watch (x, (newX) => { console.log(`x값: ${newX}`) } //인자: 반응형 객체 x
    watch ( () => x.value + y.value, (sum) => { console.log(`x + y = ${sum}` } // 인자: sum 함수

    const obj = reactive( {count: 0} );
    watch ( () => obj.count, (count) => { console.log(`count값: ${count}` }; //인자: 반응형 객체 obj의 속성을 반환하는 함수 (obj.count 자체를 인자로 쓸 수 없다)
    </script>
  </code>
</pre>

* 옵션:
-  immediate: true : 페이지 로드 시(=컴포넌트가 생성되자마자) 즉시 실행되는 옵
-  deep: true : 중첩된 변경을 감시할지 여부를 설정하는 옵션 (감시 대상이 배열 또는 객체(object)인 경우 object 내부의 변화를 감지하기 위함)
-  flush: pre/post/sync : DOM이 모두 렌더링 된 이후의 시점에서 감시 대상의 변화를 감지하기 위한 옵션
  + pre(기본): 렌더링 전에 콜백 호출
  + post: 렌더링이 끝날 때까지 콜백을 연기
  + sync: 값이 변경되는 즉시 콜백 호출(동기적) (비효율적)
> const data = ref( {count: 0} );
watch ( () => {
 data: {
  immediate: true,
  deep: true,
  flush: post
  handler(newVal) { console.log('변경이 감지됨, vale, newVal) }
});
    
