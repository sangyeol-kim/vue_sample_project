<template>
    <div class="todos">
        <ComponentTodo 
        v-for="(todo, t) in todos"
        :key="t"
        :todo="todo"
        @remove="removeTodo(t)"
        />
    </div>
</template>

<script>
import ComponentTodo from './Todo.vue'

export default {
    components: {
        ComponentTodo,
    },
    props: ['todos'],
    methods: {
        removeTodo(index) {
            this.$emit('removeTodo', index)
        },
    }
}
</script>