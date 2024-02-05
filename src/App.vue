<template>
  <ChildComp :msg="greeting" />
</template>

<!-- < Options > -->
<script>
import ChildComp from "./ChildComp.vue";
export default {
  components: { ChildComp },
  data() {
    return { greeting: "부모 컴포넌트로부터 💌을 전달받았어요!" };
  },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import { ref } from "vue";
import ChildComp from "./ChildComp.vue";

const greeting = ref("부모 컴포넌트로부터 💌을 전달받았어요!");
</script> -->

<!-- 
[Props]
자식 컴포넌트는 props를 통해 부모로부터 데이터를 받을 수 있습니다.
우선, 허용할 props를 선언해야 합니다.

< ChildComp.vue >
1. Options
<script>
export default {
  props: {msg: String}
}
</script>

2. Composition
<script setup>
  const props = defineProps({msg: String})
</script>

참고로 defineProps()는 컴파일 타임 매크로이므로 import 할 필요가 없습니다.
일단 선언되면 msg prop은 자식 컴포넌트 템플릿에서 사용할 수 있습니다.
또한 defineProps()에서 반환된 객체는 JavaScript에서 접근할 수 있습니다.

부모는 속성을 사용하는 것처럼 자식에게 prop을 전달할 수 있습니다.
동적 값을 전달하기 위해 v-bind 문법을 사용할 수도 있습니다.

< ChildComp :msg="greeting"/>
 -->
