<template>
  <ChildComp @response="(msg) => (childMsg = msg)" />
  <p>{{ childMsg }}</p>
</template>

<!-- < Options > -->
<script>
import ChildComp from "./ChildComp.vue";

export default {
  components: { ChildComp },
  data() {
    return { childMsg: "자식 컴포넌트로부터 아직 메시지를 받지 못했어요!" };
  },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import { ref } from "vue";
import ChildComp from "./ChildComp.vue";

const childMsg = ref("자식 컴포넌트로부터 아직 메시지를 받지 못했어요!");
</script> -->

<!-- 
[Emit]

자식 컴포넌트는 부모로부터 props를 받는 것 뿐만 아니라 이벤트를 emit(발송)할 수도 있습니다.
1. Options
<script>
  export default {
    emits:['response'],
    created() {
      this.$emit('response', '자식 컴포넌트로부터 🌷를 받았어요!)
    }
  }
</script>

2. Composition
<script setup>
  // emit할 이벤트 선언
  const emit = defineEmits(['response']);

  // 인자와 함께 emit
  emit('response', '자식 컴포넌트로부터 🌷를 받았어요!');
</script>

emit()의 첫 번째 인자는 이벤트 이름입니다. 이후 추가되는 모든 인자는 이벤트 리스너에 전달됩니다.

부모는 v-on을 사용하여 자식이 발송한 이벤트를 수신할 수 있습니다.
아래 예제 코드는 자식이 이벤트를 발송할 때 추가한 인자를 핸들러에서 받아 로컬 상태에 할당한 것입니다.
<ChildComp @response="(msg) => childMsg = msg"/>
 -->
