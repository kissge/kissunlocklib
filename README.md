# kissunlocklib

TypeScript で書かれた小さなライブラリです。

## 使い方

このライブラリはビルド済み JavaScript を公開せず、TypeScript のソースを
そのまま配布します。`package.json` の `exports` と `types` は
`src/index.ts` を参照するため、TypeScript 対応の bundler や実行環境からは
関数の型が推論されます。

```ts
import { greet } from "kissunlocklib";

const message = greet("World");
// message: string
```

### GitHub から利用する場合

GitHub リポジトリを依存関係に追加します。

```json
{
  "dependencies": {
    "kissunlocklib": "github:<owner>/<repository>"
  }
}
```

利用側の bundler またはランタイムが `.ts` ファイルを直接扱えることが必要です。
通常の Node.js が TypeScript を実行する場合は、利用側で TypeScript の
トランスパイル設定を用意してください。

## 開発

依存関係をインストール後、型チェック・lint・フォーマットチェックを実行します。

```sh
pnpm install
pnpm run check
```

フォーマットを適用する場合は、次を実行します。

```sh
pnpm run format
```
