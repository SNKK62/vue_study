# Props
```javascript
// in child component
export default {
  props: {
    msg: String
  }
}
```
- 子コンポーネントで`props`を定義する
```vue
<ChildComp :msg="greeting" />
```
```vue:App.vue
<script>
import ChildComp from './ChildComp.vue'

export default {
  components: {
    ChildComp
  },
  data() {
    return {
      greeting: 'Hello from parent'
    }
  }
}
</script>

<template>
  <ChildComp :msg="greeting" />
</template>
```
```vue:ChildComp.vue
<script>
export default {
  props: {
    msg: String
  }
}
</script>

<template>
  <h2>{{ msg || 'No props passed yet' }}</h2>
</template>
```
