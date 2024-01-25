<!-- < Options > -->
<script>
export default {
  data() {
    return { awesome: true };
  },
  methods: {
    toggle() {
      this.awesome = !this.awesome;
    },
  },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import { ref } from "vue";

const awesome = ref(true);

function toggle() {
  awesome.value = !awesome.value;
}
</script> -->

<template>
  <button @click="toggle">토글 버튼</button>
  <h1 v-if="awesome">Vue는 굉장해! 엄청나!</h1>
  <h1 v-else>오 안돼 😢</h1>
</template>

<!-- 
[ 조건부 렌더링 ]

엘리먼트를 조건부로 렌더링하기 위해 v-if 디렉티브를 사용할 수 있습니다.
<h1 v-if="awesome">Vue는 굉장해! 엄청나!</h1>

이 <h1>은 awesome의 값이 truthy인 경우에만 렌더링됩니다.
awesome이 falsy 값으로 변경되면 DOM에서 제거됩니다.

또한 v-else 및 v-else-if를 사용하여 조건의 다른 분기를 나타낼 수도 있습니다.
<h1 v-if="awesome">Vue는 굉장해! 엄청나!</h1>
<h1 v-else>오 안돼 😢</h1>

참고 : https://ko.vuejs.org/guide/essentials/conditional
 -->
