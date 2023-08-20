# リアクティビティ
## nextTick
```vue
import { nextTick } from 'vue'

export default {
  methods: {
    async increment() {
      this.count++
      await nextTick()
      // DOM が更新されました
    }
  }
}
```
## ステートフルなメソッド
```vue
import { debounce } from 'lodash-es'

export default {
  methods: {
    // Lodash を使ったデバウンス
    click: debounce(function () {
      // ... クリックに対する反応 ...
    }, 500)
  }
}
```
```vue
export default {
  created() {
    // 各インスタンスがデバウンスされたハンドラーのコピーを持つようになりました。
    this.debouncedClick = _.debounce(this.click, 500)
  },
  unmounted() {
    // また、タイマーをキャンセルするのも良いアイデアです
    // コンポーネントを取り外したとき
    this.debouncedClick.cancel()
  },
  methods: {
    click() {
      // ... クリックに対する反応 ...
    }
  }
}
```
