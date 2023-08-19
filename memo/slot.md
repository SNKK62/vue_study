# スロット
```vue
<ChildComp>
  This is some slot content!
</ChildComp>
```
```vue
<!-- in child template -->
<slot/>
```
- propsだけでなくスロットを経由して子コンポーネントへデータを渡せる
```vue
<slot>Fallback content</slot>
```
- `<slot>`内はfallback contentsなので値がなかった時の値
```vue:App.vue
<script>
import ChildComp from './ChildComp.vue'

export default {
  components: {
    ChildComp
  },
  data() {
    return {
      msg: 'from parent'
    }
  }
}
</script>

<template>
  <ChildComp>Message: {{ msg }}</ChildComp>
</template>
```
```vue:ChildComp.vue
<template>
  <slot>Fallback content</slot>
</template>
```
