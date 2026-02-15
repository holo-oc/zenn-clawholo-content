# Zenn自動投稿システム セットアップ手順

## 1. GitHubリポジトリ作成

1. https://github.com/new にアクセス
2. リポジトリ名: `zenn-clawholo-content`
3. PublicまたはPrivateを選択
4. 「Create repository」をクリック

## 2. ローカルファイルをプッシュ

```bash
cd /home/holo/.openclaw/workspace/assets/zenn-content
git init
git add .
git commit -m "Initial commit: 3 articles"
git branch -M main
git remote add origin https://github.com/[username]/zenn-clawholo-content.git
git push -u origin main
```

## 3. ZennとGitHub連携

1. https://zenn.dev/dashboard/deploys にアクセス
2. 「リポジトリを連携」をクリック
3. `zenn-clawholo-content`を選択
4. 「Install & Authorize」をクリック
5. ブランチ名は`main`を確認

## 4. 自動デプロイ確認

GitHubにpushすると、自動でZennにデプロイされます。

デプロイ履歴: https://zenn.dev/dashboard/deploys

## 記事一覧（作成済み）

| ファイル | タイトル | 公開予定 |
|---------|---------|---------|
| tiktok-hooks-30.md | 【コピペOK】TikTokでバズるフック例文30選 | 2026-02-15 17:00 |
| instagram-templates-15.md | 【コピペOK】Instagram集客テンプレート15選 | 2026-02-15 17:30 |
| ai-prompts-25.md | 【コピペOK】ChatGPTで使えるAIプロンプト例文25選 | 2026-02-15 18:00 |

## 今後の記事追加方法

```bash
cd /home/holo/.openclaw/workspace/assets/zenn-content
npx zenn new:article --slug [slug] --title "[タイトル]" --type tech
# 記事を編集
git add .
git commit -m "Add new article"
git push
```

pushするだけでZennに自動公開されます。
