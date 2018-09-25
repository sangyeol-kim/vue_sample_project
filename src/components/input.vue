<template>
    <div class="input">
        <input type="text" v-model="inputText" />
        <button @click="addTodo">추가</button>
    </div>
</template>

<script>
export default {
  data() {
    return {
      inputText: ''
    }
  },
  methods: {
    addTodo() {
      this.$emit("addTodo", this.inputText)
      this.inputText = ''
    }
  },
}
</script>