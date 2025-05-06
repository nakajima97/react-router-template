# React Router v7 テンプレート

このリポジトリは、React Router v7 を使ってアプリを開発する際のテンプレートです。

## 特徴

- 🚀 サーバーサイドレンダリング対応
- ⚡️ ホットリロード（HMR）
- 📦 アセットバンドル・最適化
- 🔄 データローディング・ミューテーション
- 🔒 TypeScript 対応
- 🎉 TailwindCSS 標準搭載
- 📖 [React Router ドキュメント](https://reactrouter.com/)

## はじめかた

### インストール

```bash
# 依存パッケージをインストール
yarn install
```

### 開発サーバー起動

```bash
yarn dev
```

アプリは `http://localhost:5173` で起動します。

### 型定義の自動生成

このテンプレートでは `.react-router` ディレクトリ配下の型ファイルが自動生成されます。
CI環境等で型チェックを行う場合は、以下のコマンドを事前に実行してください。

```bash
yarn react-router typegen
```

または、型チェックと同時に生成する場合は:

```bash
yarn type-check
```

## 本番ビルド

```bash
yarn build
```

## デプロイ

### Docker を使う場合

```bash
docker build -t my-app .
docker run -p 3000:3000 my-app
```

### Node アプリとしてデプロイする場合

`yarn build` で生成される `build/` ディレクトリをデプロイ対象にしてください。

```
├── package.json
├── yarn.lock
├── build/
│   ├── client/    # 静的アセット
│   └── server/    # サーバーサイドコード
```

## スタイリング

[Tailwind CSS](https://tailwindcss.com/) が初期設定済みです。お好みのCSSフレームワークに差し替えも可能です。

---

Built with ❤️ using React Router v7.
