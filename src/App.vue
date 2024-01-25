<!-- < Options > -->
<script>
export default {
  data() {
    return { count: 0 };
  },
  methods: {
    increment() {
      this.count++;
    },
  },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import { ref } from "vue";

const count = ref(0);

function increment() {
  count.value++;
}
</script> -->

<template>
  <button @click="increment">숫자 세기 {{ count }}</button>
</template>

<style></style>

<!-- 
[이벤트 리스너]
v-on 디렉티브를 사용하여 DOM 이벤트를 수신할 수 있습니다.
<button v-on:click="increment">{{ count }}</button>

자주 사용되기 때문에 v-on에는 다음과 같은 단축 문법도 있습니다.
<button @click="increment">{{ count }}</button>

함수 내에서 ref 값을 변경하여 컴포넌트 상태를 업데이트 할 수 있습니다.
이벤트 핸들러는 인라인 표현식을 사용할 수도 있으며, 수식어를 사용하여 일반적인 작업을 단순화할 수 있습니다.
참고 : https://ko.vuejs.org/guide/essentials/event-handling

 -->
