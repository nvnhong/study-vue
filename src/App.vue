<template>
  <ChildComp />

  <ChildComp>
    {{ msg }}
  </ChildComp>
</template>

<!-- < Options > -->
<script>
import ChildComp from "./ChildComp.vue";
export default {
  components: { ChildComp },
  data() {
    return { msg: "Vue는 개발자에게 정말 유용하죠! 🎁" };
  },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import ChildComp from "./ChildComp.vue";
import { ref } from "vue";

const msg = ref("Vue는 개발자에게 정말 유용하죠! 🎁");
</script> -->

<!-- 
[슬롯]
부모 컴포넌트는 자식에게 props를 사용하여 데이터를 전달하는 것 외에도, 슬롯을 사용하여 템플릿 조각을 전달할 수 있습니다.
<ChildComp>
  이것은 슬롯 컨텐츠입니다!
</ChildComp>

자식 컴포넌트가 <slot> 엘리먼트를 "발산 수단(outlet: 가이드에서 '아울렛'으로 표기됨)"으로 사용하면, 부모에게 전달 받은 슬롯 컨텐츠를 렌더링할 수 있습니다.
<slot/>

<slot> 아울렛 내부 컨텐츠는 "대체" 컨텐츠로 처리될 수 있는데, 부모가 슬롯 컨텐츠를 전달하지 않은 경우에 표시됩니다.
<slot>대체: 부모로부터 컨텐츠를 못 받았어요! 😢</slot>
 -->
