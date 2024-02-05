<template>
  <h2>{{ msg || "prop이 아직 전달되지 않았습니다." }}</h2>
</template>

<!-- Options -->
<script>
export default {
  props: { msg: String },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
const props = defineProps({ msg: String });
</script> -->
