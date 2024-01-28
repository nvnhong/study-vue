<!-- < Option > -->
<script>
export default {
  data() {
    return {
      todoId: 1,
      todoData: null,
    };
  },
  methods: {
    async fetchData() {
      this.todoData = null;
      const res = await fetch(
        `https://jsonplaceholder.typicode.com/todos/${this.todoId}`
      );
      this.todoData = await res.json();
    },
  },
  mounted() {
    this.fetchData();
  },
  watch: {
    todoId() {
      this.fetchData();
    },
  },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import { ref, watch } from "vue";

const todoId = ref(1);
const todoData = ref(null);

async function fetchData() {
  todoData.value = null;
  const res = await fetch(
    `https://jsonplaceholder.typicode.com/todos/${todoId.value}`
  );
  todoData.value = await res.json();
}

fetchData();

watch(todoId, fetchData);
</script> -->

<template>
  <p>할 일 id : {{ todoId }}</p>
  <button @click="todoId++" :disabled="!todoData">다음 할 일 가져오기</button>
  <p v-if="!todoData">로딩...</p>
  <p v-else>{{ todoData }}</p>
</template>

<!-- 
[ 감시자 ]
때때로 우리는 반응형 '사이드 이펙트'를 수행해야 합니다.
예를 들어 숫자가 변경될 때마다, 콘솔 로그로 출력하는 것입니다.
우리는 watch(감시자)로 이를 구현할 수 있습니다.

< Option >
export default {
  data() {
    return {
      count: 0
    }
  },
  watch: {
    count(newCount) {
      console.log(`새로 센 숫자 값은 ${this.count}`)
    }    
  }
}

< Composition >
import {ref, watch} from 'vue';

const count = ref(0);

watch(count, (newCount) => {
  console.log(`새로 센 숫자 값은 ${newCount}`)
})

watch()는 ref를 직접 감시할 수 있으므로, count의 값이 변경될 때마다 콜백이 실행됩니다.
watch()는 다른 타입의 데이터 소스도 볼 수 있습니다.
참고 : https://ko.vuejs.org/guide/essentials/watchers
 -->
