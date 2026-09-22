# qiira-content

Qiitaに投稿した記事をGitHubで管理するためのリポジトリです。

Qiita CLIを利用して、Qiita上の記事をローカル環境に同期し、
MarkdownファイルとしてGitHubで管理しています。

## 📚 記事について

Qiitaに投稿した記事は `public/` ディレクトリで管理しています。

```text
public/
├── xxxxxxxxxxxxxxxxxxxx.md
├── xxxxxxxxxxxxxxxxxxxx.md
└── ...
```

## 🛠 使用ツール

- Qiita CLI
- Node.js
- Git / GitHub

## 🚀 Qiita CLI

Qiita CLIが正常に利用できるか確認します。

```bash
npx qiita version
```

ローカルで記事をプレビューする場合は、以下を実行します。

```bash
npx qiita preview
```

起動後、表示されたURLへブラウザからアクセスします。

## 🔄 Qiitaの記事をGitHubへ反映する

Qiita上で記事を新規公開・更新した場合は、以下の手順でGitHubへ反映します。

### 1. Qiitaの記事を取得

```bash
npx qiita pull
```

### 2. 変更内容を確認

```bash
git status
```

必要に応じて差分も確認します。

```bash
git diff
```

### 3. Gitへ追加

```bash
git add .
```

### 4. コミット

```bash
git commit -m "Update Qiita articles"
```

### 5. GitHubへ反映

```bash
git push
```

基本的には以下の流れで運用します。

```text
Qiitaで記事を公開・更新
        ↓
npx qiita pull
        ↓
git status / git diff
        ↓
git add .
        ↓
git commit
        ↓
git push
        ↓
GitHubへ反映
```

## 📝 ローカルで記事を書く場合

Qiita CLIを利用して、新しい記事を作成することもできます。

```bash
npx qiita new 記事のファイル名
```

作成した記事は `public/` に保存されます。

記事を編集しながら確認する場合は、

```bash
npx qiita preview
```

を利用します。

## 📁 Git管理について

以下のファイル・ディレクトリはGitの管理対象外としています。

```gitignore
node_modules/
public/.remote/
.DS_Store
```

`public/.remote/` はQiita CLIが利用する同期用のデータのため、
GitHubでは管理しません。

## 🔗 Links

- [Qiita](https://qiita.com/)
- [Qiita CLI](https://github.com/increments/qiita-cli)