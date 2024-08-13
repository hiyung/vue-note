계산된 속성
=============
(Composition API)

### #computed()
* 사용법:
  - import { computed } from "vue";
  - 기본적으로 getter 함수만 있지만, 필요해 의해 setter 함수도 설정 가능하다
  -method와 동일한 결과를 보여주지만, **반응적 의존관계에 의해 캐쉬 된다** 는 점이 다르다
* 주의할 점:
  - getter에서 side effect는 금지
  - computed의 값을 다시 변경하지 말 것(읽기 전용과 동일함)
<pre>
  <code>
    <script setup>
    import { computed } from "vue";

    const me = ref({
      name: "Hee Young",
      info: [32, 'Female', 'Married']
    });
    const updateMe = computed(() => {
      return me.info.length > 0 ? "Yes" : "No" //getter
    });
    </script>

    <template>
    <p>{{ me.name }}</p>
    <span>{{ updateMe }}</span>
    </template>
  </code>
</pre>
> 해석 :updateMe()는 여러번 재사용 가능하고, 변수 me의 값이 변하지 않는 이상 updateMe()는 이미 계산된(실행된) 값을 동일하게 반환한다 
