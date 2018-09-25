<template>
    <div class="todo">
        <span class="todo__contents" :style="todoContentsStyle"> {{todo.contents}} </span>
        <button @click="complete">완료</button>
        <button @click="remove">삭제</button>
    </div>
</template>

<script>
export default {
    props: ['todo'],
    computed: {
        todoContentsStyle() {
            if (this.todo.isCompleted === true) {
                return {
                    textDecoration: 'line-through',
                    color: "#aaa",
                }
            } else {
                return {}
            }
        }
    },
    methods: {
        complete() {
            this.todo.isCompleted = true 
        },
        remove() {
            this.$emit('remove')
        },
    }
}

</script>
