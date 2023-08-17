# イベントリスナー
```vue
<button v-on:click="increment">{{ count }}</button>
```
- `v-on` ディレクティブでDOMイベントをsubscribe
```vue
<button @click="increment">{{ count }}</button>
```
- 頻繁に使われるので省略可能
```vue
<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increment() {
      this.count++
    }
  }
}
</script>

<template>
  <button @click="increment">count is: {{ count }}</button>
</template>
```
