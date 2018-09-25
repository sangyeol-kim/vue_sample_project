<template>
    <div class="app">
        <ComponentInput @addTodo="addTodo($event)" />
        <ComponentTodos :todos="todos" @removeTodo = "removeTodo($event)" />
    </div>
</template>

<script>
import ComponentInput from "./components/input.vue"
import ComponentTodos from "./components/Todos.vue"

export default {
  components: {
    ComponentInput,
    ComponentTodos
  },
  data() {
    return {
      todos: [],
    }
  },
  methods: {
    addTodo(todoContents) {
      this.todos.unshift({
          contents: todoContents,
          isCompleted: false,
      })
      //여기서 this.todos에 추가
    },
    removeTodo(index) {
        this.todos.splice(index, 1)
    },
  },
}
</script>