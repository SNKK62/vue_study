# 条件付きレンダリング
```vue
<h1 v-if="awesome">Vue is awesome!</h1>
```
```vue
<h1 v-if="awesome">Vue is awesome!</h1>
<h1 v-else>Oh no 😢</h1>
```
- `v-else` `v-else-if` もある
```vue
<script>
export default {
  data() {
    return {
      awesome: true
    }
  },
  methods: {
    toggle() {
      this.awesome = !this.awesome
    }
  }
}
</script>

<template>
  <button @click="toggle">toggle</button>
  <h1 v-if="awesome">Vue is awesome!</h1>
  <h1 v-else>Oh no 😢</h1>
</template>
```
