<!-- < Option > -->
<script>
import ChildComp from "./ChildComp.vue";

export default {
  components: { ChildComp },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import ChildComp from "./ChildComp.vue";
</script> -->

<template>
  <ChildComp />
</template>

<!-- 
[컴포넌트]
일반적으로 실제 Vue 앱은 중첩된 컴포넌트를 사용하여 생성됩니다.

상위 컴포넌트는 다른 컴포넌트를 템플릿의 하위 컴포넌트로 렌더링할 수 있습니다.
자식 컴포넌트를 사용하려면 먼저 가져와야 합니다.

< Option >
import ChildComp from './ChildComp.vue'
export default {
  components: {
    ChildComp
  }
}

< Composotion >
import ChildComp from './ChildComp.vue'
<ChildComp />
 -->
