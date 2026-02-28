# Cloudflare Pages テストサイト

Cloudflare PagesにデプロイするためのシンプルなHTML/CSSサイトです。

## ファイル構成

- `index.html` - メインのHTMLファイル
- `styles.css` - スタイルシート
- `.gitignore` - Git除外設定
- `README.md` - このファイル

## デプロイ方法

### GitHub連携でのデプロイ（推奨）

#### 1. GitHubリポジトリの準備

```bash
# Gitリポジトリを初期化（まだの場合）
git init

# ファイルをステージング
git add .

# 初回コミット
git commit -m "Initial commit: Cloudflare Pages test site"

# GitHubにリポジトリを作成し、リモートを追加
# （GitHub上でリポジトリを作成後）
git remote add origin https://github.com/ユーザー名/リポジトリ名.git

# プッシュ
git branch -M main
git push -u origin main
```

#### 2. Cloudflare Pagesでの設定

1. [Cloudflare Dashboard](https://dash.cloudflare.com/)にログイン
2. 左メニューから **Pages** を選択
3. **Create a project** をクリック
4. **Connect to Git** を選択
5. GitHubアカウントを認証・連携
6. 作成したリポジトリを選択
7. プロジェクト設定：
   - **Project name**: 任意の名前（例: `cf-test-webpage`）
   - **Production branch**: `main` または `master`
   - **Build command**: **空欄のまま**（静的サイトのため不要）
   - **Build output directory**: **空欄のまま** または `/`
8. **Save and Deploy** をクリック

#### 3. デプロイ完了

数分でデプロイが完了し、`https://プロジェクト名.pages.dev` のURLでアクセスできます。

#### 4. 今後の更新

GitHubにプッシュするだけで、自動的に再デプロイされます：

```bash
git add .
git commit -m "Update content"
git push
```

## 注意事項

- 静的サイトなのでビルドコマンドは不要です
- `index.html` がルートに配置されている必要があります
- GitHubにプッシュすると自動的に再デプロイされます
