<!--
Say Hello World with Vue!
-->

<template>
  <h1>{{ message }}</h1>
</template>

<!-- < Options > -->
<script>
export default {
  data() {
    return { message: "Hello world" };
  },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import { ref } from "vue";

const message = ref("Hello world");
</script> -->

<!-- 
A "ref" is a reactive data source that stores a value. 
Technically, we don't need to wrap the string with ref() in order to display it, 
but we will see in the next example why it is needed if we ever intend to change the value.

<번역>
'ref'는 value를 저장하는 반응영 데이터 소스이다.
기술적으로 문자열을 보여주기 위해 ref()로 래핑할 필요는 없지만,
다음 예시를 통해 왜 value를 변경하기 위해 ref()가 필요한지 볼 것이다.
-->
