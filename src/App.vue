<!-- < Options > -->
<!-- <script>
export default {
  mounted() {
    // 이제 컴포넌트가 마운트 되었습니다.
    this.$refs.pElementRef.textContent = "생명주기와 템플릿 참조";
  },
};
</script> -->

<!-- < Composition > -->
<script setup>
import { ref, onMounted } from "vue";

const pElementRef = ref(null);

onMounted(() => {
  // 이제 컴포넌트가 마운트 되었습니다.
  pElementRef.value.textContent = "생명주기와 템플릿 참조";
});
</script>

<template>
  <p ref="pElementRef">안녕</p>
</template>

<!-- 
[생명주기와 템플릿 참조]
지금까지 Vue는 반응형 및 선언적 렌더링으로 모든 DOM 업데이트를 처리해 왔습니다.
그러나 필연적으로 DOM을 수동으로 작업해야 하는 경우가 있습니다.

우리는 특별한 속성인 ref를 사용하여 템플릿 참조를 요청할 수 있습니다.
<p ref="pElementRef">안녕</p>

1. Option 에서 
엘리먼트는 this.$refs에 this.$refs.pElementRef 로 노출됩니다.
그러나 컴포넌트가 마운트된 후에만 접근할 수 있습니다.

마운트된 후, 코드를 실행하려면 mounted 옵션을 사용해야 합니다.
export default {
  mounted() {
    // 이제 컴포넌트가 마운트 되었습니다.
  }
}

2. Composition 에서
참조에 접근하려면 다음과 같이 이름이 일치하는 ref를 선언해야 합니다.
const pElementRef = ref(null);

ref는 null 값으로 초기화합니다.
<script setup> 실행 시 해당 엘리먼트가 아직 존재하지 않기 때문입니다.
템플릿 참조는 컴포넌트가 마운트된 후에만 접근할 수 있습니다.

마운트 된 후, 코드를 실행하려면 onMounted() 함수를 사용해야 합니다.
import { onMounted } from 'vue'
onMounted(() => {
  // 이제 컴포넌트가 마운트 되었습니다.
})

이것을 생명 주기 훅이라고 하며, 생명 주기의 특정 시간에 호출할 콜백을 등록할 수 있습니다.
created 및 updated와 같은 다른 훅도 있습니다.
참고 : https://ko.vuejs.org/guide/essentials/lifecycle#lifecycle-diagram
 -->
