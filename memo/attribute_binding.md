# 属性バ:インディング
```vue
<div v-bind:id="dynamicId"></div>
```
- Vue では`{{ }}` の中はテキスト補完のみ使用
- 動的な値を属性にバインドするには`v-bind` ディレクティブを使う
- ディレクティブは `v-` から始まる特別な属性
```vue
<div :id="dynamicId"></div>
```
- `v-bind` は頻繁に使うので省略可能
```vue
<MyComponent class="baz" />
```
```vue
<!-- $attrs を使った MyComponent のテンプレート -->
<p :class="$attrs.class">Hi!</p>
<span>This is a child component</span>
```
- `$attrs.[property]`でプロパティを参照できる
```vue
<script>
export default {
  data() {
    return {
      titleClass: 'title'
    }
  }
}
</script>

<template>
  <h1 :class="titleClass">Make me red</h1>
</template>

<style>
.title {
  color: red;
}
</style>
```
