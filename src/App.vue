<!-- < Options > -->
<script>
export default {
  data() {
    return { text: "" };
  },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import { ref } from "vue";

const text = ref("");
</script> -->

<template>
  <input v-model="text" placeholder="여기에 입력하기" />
  <!-- <input :value="text" @input="onInput" placeholder="여기에 입력하기" /> -->
  <p>{{ text }}</p>
</template>

<!-- 
폼(form) 바인딩

v-bind와 v-on을 함께 사용하면, 폼 안의 입력 엘리먼트에 양방향 바인딩을 만들 수 있습니다.
<input :value="text" @input="onInput" />

function onInput(event) {
  // v-on 핸들러는 네이티브 DOM 이벤트를 인자로 받는다.
  text.value = e.target.value;
}

Vue는 양방향 바인딩을 간소화하기 위해, v-model이라는 디렉티브를 제공합니다.
이것은 위 내용에 대한 단축 표기법입니다.
<input v-model="text"/>

v-model은 <input>의 값을 바인딩된 상태와 자동으로 동기화하므로, 더 이상 이에 대한 이벤트 핸들러를 사용할 필요가 없습니다.
참고 : https://ko.vuejs.org/guide/essentials/forms
 -->
