<!--
Here we are reactively binding element attributes / properties to the state.
The :title syntax is short for v-bind:title.
-->

<template>
  <p>
    <span :title="message">
      Hover your mouse over me for a few seconds to see my dynamically bound title!
    </span>
  </p>
  
  <!--
  class bindings have special support for objects and arrays
  in addition to plain strings
  -->
  <p :class="{red: isRed}" @click="toggleRed">
    This should be red... but click me to toggle it.
  </p>

  <!--
  style bindings also support object and arrays
  여기서 중괄호 {}를 사용하는 것은 객체 리터럴을 생성하는데,
  객체의 키는 스타일 속성이 되고, 값은 해당 스타일 속성에 바인딩할 데이터 변수가 됩니다
  -->
  <p :style="{color}" @click="toggleColor">
    This should be green, and should toggle between green and blue on click.
  </p>
</template>

<script>
export default {
  data() {
    return {
      message: 'Hello World!',
      isRed: true,
      color: 'green'
    }
  },
  methods: {
    toggleRed() {
      this.isRed = !this.isRed
    },
    toggleColor() {
      this.color = this.color === 'green' ? 'blue' : 'green'
    }
  }
}
</script>

<!--<script setup>-->
<!--import {ref} from "vue";-->

<!--const message = ref('Hello World!');-->
<!--const isRed = ref(true);-->
<!--const color = ref('green')-->

<!--function toggleRed() {-->
<!--  isRed.value = !isRed.value;-->
<!--}-->

<!--function toggleColor() {-->
<!--  color.value = color.value === 'green' ? 'blue' : 'green'-->
<!--}-->
<!--</script>-->

<style>
.red {
  color: red;
}
</style>