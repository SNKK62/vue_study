# ライフサイクルとテンプレート参照
```vue
<p ref="pElementRef">hello</p>
```
- `this.$refs.pElementRef` で参照できる
```javascript
export default {
  mounted() {
    // コンポーネントがマウントされました。
  }
}
```
- `mounted` でマウント後の処理を書ける
- 他にも`updated`や`created`がある
```vue
<script>
export default {
  mounted() {
    this.$refs.pElementRef.textContent = 'mounted!'
  }
}
</script>

<template>
  <p ref="pElementRef">hello</p>
</template>
```
