# ウォッチャー
```vue
export default {
  data() {
    return {
      count: 0
    }
  },
  watch: {
    count(newCount) {
      // そう、console.log() は副作用です
      console.log(`new count is: ${newCount}`)
    }
  }
}
```
- `watch`オプションを使うと副作用をリアクティブに実行できる
```vue
<script>
export default {
  data() {
    return {
      todoId: 1,
      todoData: null
    }
  },
  methods: {
    async fetchData() {
      this.todoData = null
      const res = await fetch(
        `https://jsonplaceholder.typicode.com/todos/${this.todoId}`
      )
      this.todoData = await res.json()
    }
  },
  mounted() {
    this.fetchData()
  },
  watch: {
    todoId() {
      this.fetchData()
    }
  }
}
</script>

<template>
  <p>Todo id: {{ todoId }}</p>
  <button @click="todoId++">Fetch next todo</button>
  <p v-if="!todoData">Loading...</p>
  <pre v-else>{{ todoData }}</pre>
</template>
```
