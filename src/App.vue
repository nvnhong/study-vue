<script setup>
import { ref } from "vue";
import { reactive } from "vue";

// script에서 ref에 접근할 때 .value를 사용한다.
const message1 = ref("안녕 Vue!");
console.log(message1.value);
message1.value = "메세지 변경됨";
console.log(message1.value);

const message2 = ref("Hello World");
const counter = reactive({ count: 10 });
</script>

<template>
  <p>message1 : {{ message1 }}</p>
  <p>message2 : {{ message2 }}</p>
  <p>count : {{ counter.count }}</p>
</template>

<!-- 
[선언적 렌더링]

SFC(Single File Component)는 HTML, CSS, Javascript를 캡슐화한 코드 블록으로 재사용 가능한 .vue 파일입니다.

Vue의 핵심 기능은 선언적 렌더링입니다. 
HTML을 확장하는 템플릿 문법을 사용하여 JavaScript 상태를 기반으로 HTML이 어떻게 보이는지 설명할 수 있습니다. 
상태가 변경되면 HTML이 자동으로 업데이트 됩니다.

변경 시, 업데이트를 트리거할 수 있는 상태는 반응형으로 간주됩니다.
Vue의 reactive() API를 사용하여 반응형 상태를 선언할 수 있습니다.
reactive()로 생성된 객체는 일반 객체처럼 작동하는 JavaScript 프락시입니다.

reactive()는 객체(배열, Map, Set과 같은 빌트인 타입 포함)에서만 작동합니다.
반면에 ref()는 모든 타입의 값을 사용할 수 있으며, .value 속성으로 내부 값을 노출하는 객체를 생성합니다.

컴포넌트의 <script setup> 블록에 선언된 반응형 상태는 템플릿에서 직접 사용할 수 있습니다.
템플릿에서 선언된 ref 값에 접근할 때 .value를 사용할 필요가 없습니다.
보다 간결한 사용을 위해 자동으로 언래핑됩니다.
 -->
