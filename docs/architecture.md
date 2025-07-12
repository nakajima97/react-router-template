# プロジェクト構造と設計方針
## ディレクトリ構成
```
docs/                  # ドキュメント
public/                # 静的ファイル
app/                   # React Router アプリディレクトリ
├── routes/               # ルート定義（ファイルベースルーティング）
│   ├── index.tsx         # '/' に対応
│   ├── about.tsx         # '/about' に対応
│   └── users/
│       ├── index.tsx     # '/users' に対応
│       └── $id.tsx       # '/users/:id' に対応（動的ルート）
├── components/        # 再利用可能な UI コンポーネント (アプリ全体で共有)
│   ├── shadcn/        # shadcn/ui コンポーネント
│   │   ├── ui/        # shadcn/ui の基本コンポーネント
│   │   │   ├── button.tsx
│   │   │   ├── input.tsx
│   │   │   └── ...
│   │   └── index.ts   # コンポーネントのエクスポート
│   ├── presentational/  # プレゼンテーショナルコンポーネント
│   │   ├── ComponentName/ # 例: Button, Input, Header など
│   │   │   ├── index.tsx
│   │   │   └── ComponentName.stories.tsx
│   │   └── ...
│   ├── containers/     # コンテナコンポーネント
│   │   ├── ContainerName/
│   │   │   ├── index.tsx
│   │   │   └── useContainerHook.ts
│   │   └── ...
│   └── ...
├── features/          # 特定の機能に関するコンポーネント、ロジック、ページ
│   ├── featureName/   # 例: auth, productList, checkout など
│   │   ├── presentational/  # 機能固有の Presentational Components
│   │   │   ├── ComponentName/
│   │   │   │   ├── index.tsx
│   │   │   │   └── ComponentName.stories.tsx
│   │   │   └── ...
│   │   ├── containers/     # 機能固有の Container Components (ロジックと状態管理)
│   │   │   ├── ContainerName/
│   │   │   │   ├── index.tsx
│   │   │   │   └── useContainerHook.ts  # コンテナ用のカスタムフック
│   │   │   └── ...
│   │   ├── hooks/          # 機能固有のカスタムフック
│   │   ├── types/          # 機能固有の型定義
│   │   ├── lib/            # 機能固有の外部ライブラリの設定やラッパー
│   │   ├── services/       # 機能固有の外部サービスとの通信を担当するレイヤー
│   │   └── utils/          # 機能固有のユーティリティ関数
│   └── ...
├── hooks/             # アプリ全体で共有するカスタム React フック
├── types/             # アプリ全体で使用する型定義
├── lib/               # 外部ライブラリの設定やラッパー
│   ├── clerk/         # Clerk認証の設定
│   ├── cloudflare/    # Cloudflare関連の設定
│   └── ...
├── services/          # 外部サービスとの通信を担当するレイヤー
│   ├── api/          # APIクライアント
│   │   ├── client.ts # APIクライアントの設定
│   │   └── endpoints/ # APIエンドポイントの定義
│   └── ...
└── utils/             # 純粋なユーティリティ関数
    ├── date.ts       # 日付操作
    ├── format.ts     # 文字列フォーマット
    └── ...
```
