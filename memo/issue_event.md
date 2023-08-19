# イベントの発行
```vue
export default {
  // 発行されるイベントを宣言します
  emits: ['response'],
  created() {
    // 引数つきで発行
    this.$emit('response', 'hello from child')
  }
}
```
- 子コンポーネントでイベントを発行できる
-`this.$emit()`の第一引数はイベント名
```vue
<ChildComp @response="(msg) => childMsg = msg" />
```
- `v-on`でイベントを購読できる
```vue:App.vue
<script>
import ChildComp from './ChildComp.vue'

export default {
  components: {
    ChildComp
  },
  data() {
    return {
      childMsg: 'No child msg yet'
    }
  }
}
</script>

<template>
  <ChildComp @response="(msg) => childMsg = msg" />
  <p>{{ childMsg }}</p>
</template>
```
```vue:ChildComp.vue
<script>
export default {
  emits: ['response'],
  created() {
    this.$emit('response', 'hello from child')
  }
}
</script>

<template>
  <h2>Child component</h2>
</template>
```
