<!-- Options -->
<script>
// 각 할 일에 고유한 id 부여
let id = 0;

export default {
  data() {
    return {
      id: 0,
      newTodo: "",
      todos: [
        { id: id++, text: "HTML 배우기" },
        { id: id++, text: "CSS 배우기" },
        { id: id++, text: "JavaScript 배우기" },
      ],
    };
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo });
      this.newTodo = "";
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((value) => todo !== value);
    },
  },
};
</script>

<!-- Composition -->
<!-- <script setup>
import { ref } from "vue";

// 각 할 일에 고유한 id 부여
let id = 0;

const newTodo = ref("");
const todos = ref([
  { id: id++, text: "HTML 배우기" },
  { id: id++, text: "CSS 배우기" },
  { id: id++, text: "JavaScript 배우기" },
]);

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value });
  newTodo.value = "";
}

function removeTodo(todo) {
  todos.value = todos.value.filter((value) => todo !== value);
}
</script> -->

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo" />
    <button>할 일 추가</button>
  </form>

  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{ todo.text }}
      <button @click="removeTodo(todo)">삭제</button>
    </li>
  </ul>
</template>

<!-- 
[ 리스트 렌더링 ]

v-for 디렉티브를 사용하여 자료 배열을 엘리먼트 목록으로 렌더링할 수 있습니다.
<ul>
  <li v-for="todo in todos" :key="todo.id">{{ todo.text }}</li>
</ul>

여기서 todo는 현재 반복 중인 배열 엘리먼트를 나타내는 로컬 변수입니다.
함수 범위와 유사하게 v-for 엘리먼트 위 또는 내부에서만 액세스할 수 있습니다.

각 todo 객체에 고유한 id를 부여하고, 각 <li>에 특별한 속성인 key를 바인딩했습니다.
key를 사용하면 Vue가 각 <li>를 정확하게 이동시켜 배열에서 해당 객체의 위치와 일치하도록 할 수 있습니다.
 -->
