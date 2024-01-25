<!-- Option -->
<script>
let id = 0;

export default {
  data() {
    return {
      newTodo: "",
      hideCompleted: false,
      todos: [
        { id: id++, text: "HTML 배우기", done: true },
        { id: id++, text: "JavaScript 배우기", done: true },
        { id: id++, text: "Vue 배우기", done: false },
      ],
    };
  },
  computed: {
    filteredTodos() {
      return this.hideCompleted
        ? this.todos.filter((t) => !t.done)
        : this.todos;
    },
  },
  methods: {
    addTodo() {
      this.todos.push({ id: id++, text: this.newTodo, done: false });
      this.newTodo = "";
    },
    removeTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo);
    },
  },
};
</script>

<!-- < Composition > -->
<!-- <script setup>
import { ref, computed } from "vue";

let id = 0;

const newTodo = ref("");
const hideCompleted = ref(false);
const todos = ref([
  { id: id++, text: "HTML 배우기", done: true },
  { id: id++, text: "JavaScript 배우기", done: true },
  { id: id++, text: "Vue 배우기", done: false },
]);

function addTodo() {
  newTodo.value.push({ id: id++, text: newTodo.value, done: false });
  newTodo.value = "";
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo);
}

const filteredTodos = computed(() => {
  return hideCompleted.value ? todos.value.filter((t) => !t.done) : todos.value;
});
</script> -->

<template>
  <form @submit,prevent="addTodo">
    <input v-model="newTodo" />
    <button>Add Todo</button>
  </form>

  <ul>
    <li v-for="todo in filteredTodos" :key="todo.id">
      <input type="checkbox" v-model="todo.done" />
      <span :class="{ done: todo.done }">{{ todo.text }}</span>
      <button @click="removeTodo(todo)">Delete</button>
    </li>
  </ul>

  <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? "Show all" : "Hide Completed" }}
  </button>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>

<!-- 
[계산된 속성]
이전 단계의 할 일 목록을 계속 만들어 나가봅시다.
여기에 이미 각 할 일에 토글 기능을 추가했습니다.
이것은 각 할 일 객체에 done 속성을 추가하고, v-model을 사용하여 체크박스에 바인딩함으로써 작동합니다.

<li v-for="todo in todos">
  <input type="checkbox" v-model="todo.done"/>
</li>

다음 개선 사항은 이미 완료된 할 일을 숨길 수 있는 기능을 추가하는 것입니다.
이미 hideCompleted 상태를 토글하는 버튼이 있습니다.
하지만 그 상태를 바탕으로 목록 내 항목을 어떻게 렌더링해야 할까요?

computed()를 소개합니다.
(Composition)반응 데이터 소스를 기반으로 .value를 계산하는 계산된 참조(ref)를 만들 수 있습니다. 
(Option) computed 옵션을 사용하여 반응적으로 계산 되는 속성을 선언할 수 있습니다.

import {ref, computed} from 'vue'

const hideCompleted = ref(false);
const todos = ref([/* ... */])

const filterTodos = computed(() => {
  // todos.value 및 hideCompleted.value를 기반으로 필터링된 할 일을 반환.
})

계산된 속성은 계산에 사용된 다른 반응형 상태를 의존성으로 추적합니다.
결과를 캐시하고 의존성이 변경되면 자동으로 업데이트합니다.
 -->
