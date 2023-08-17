# 双方向バインディング
```vue
<input :value="text" @input="onInput">
```
```vue
methods: {
  onInput(e) {
    // v-on ハンドラーはネイティブDOMのイベントを
    // 引数として受け取ります。
    this.text = e.target.value
  }
}
```
- `v-bind` と `v-on` を一緒に使って双方向バインディングできる
```vue
<input v-model="text">
```
- 双方向バインディングのsyntax sugarは`v-model` である
