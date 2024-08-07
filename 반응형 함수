반응형 함수
=============
* Composition API

### ref()
사용법:
-  import { ref } from "vue";
-  변수 선언 후 값을 ref로 감싸기
> ex: const name = ref("Hee Young");
-  변수 값 변경 시 .value에 변경할 값 넣기
> ex: const updateName = () => {name.value = "Shuan";};

### reactive()
사용법:
-  import { reactive } from "vue";
-  변수 선언 후 값을 reactive로 감싸기
> ex: const name = reactive({id: 1, //속성(property)});
-  변수 내부 속성 값 변경 시 .property에 변경할 값 넣기
> ex: const updateName = () => {name.id = 2;});

### ref 와 reactive의 차이점
* 타입제한:
  - ref: string, number, object 등 어디에도 OK
  - reactive: object, array, map, set 에서만 OK
* 접근방식(template에서 사용 시):
  - ref: .value로 값 변경 가능
  - reactive: .value 붙일 필요 없음
