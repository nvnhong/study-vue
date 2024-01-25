<!-- <script setup>
import { ref } from "vue";
const titleClass = ref("title");
</script> -->

<script>
export default {
  data() {
    return {
      titleClass: "title",
    };
  },
};
</script>

<template>
  <h1 :class="titleClass">나를 빨갛게 만들어보세요.</h1>
</template>

<style>
.title {
  color: red;
}
</style>

<!-- 
[속성 바인딩]
Vue에서 이중 중괄호는 텍스트 삽입에만 사용됩니다.
속성을 동적 값에 바인딩하려면 v-bind 디렉티브를 사용합니다.

<div v-bind:id="dynamicId"></div>

디렉티브는 v- 접두사로 시작하는 특수한 속성으로 Vue 템플릿 문법의 일부입니다.
텍스트 삽입과 유사하게 디렉티브 값은 컴포넌트의 상태에 접근할 수 있는 JavaScript 표현식입니다.

 -->
