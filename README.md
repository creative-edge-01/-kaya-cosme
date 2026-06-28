# かやのコスメ手帖

かや（@kaya）の美容・コスメ系アフィリエイトサイトです。
HTML/CSS のみで作られた**静的サイト**で、GitHub Pages で無料公開できます。

## 📁 ファイル構成

```
kaya-cosme/
├── index.html          ... トップページ
├── ranking.html        ... 人気ランキング
├── articles.html       ... 記事一覧
├── about.html          ... 運営者について
├── privacy.html        ... プライバシーポリシー・免責（アフィリ必須）
├── articles/
│   ├── sample-skincare.html  ... 記事サンプル（スキンケア）
│   └── sample-makeup.html    ... 記事サンプル（メイク）
├── css/style.css       ... デザイン（色はファイル冒頭の :root で変更可）
├── js/main.js          ... スマホメニュー開閉
└── assets/             ... 画像を入れるフォルダ
```

## ✍️ よくある編集

### アフィリエイトリンクを貼る
各ページの `href="#"` を、実際のリンクに置き換えます。

```html
<!-- 置き換え前 -->
<a class="aff-btn aff-amazon" href="#" rel="nofollow sponsored" target="_blank">Amazon</a>
<!-- 置き換え後（例） -->
<a class="aff-btn aff-amazon" href="https://amzn.to/xxxxxxx" rel="nofollow sponsored" target="_blank">Amazon</a>
```
- **Amazon** → Amazonアソシエイトの商品リンク
- **公式/楽天** → A8.net などのASP広告タグ、または楽天アフィリのリンク
- `rel="nofollow sponsored"` は広告リンクの正しい書き方なので残してください。

### 商品画像を入れる
1. 画像を `assets/` フォルダに入れる（例：`assets/item1.jpg`）
2. カード内の `<div class="thumb">商品画像</div>` を次のように書き換え：
   ```html
   <div class="thumb"><img src="assets/item1.jpg" alt="商品名"></div>
   ```
   ※ Amazon等の商品画像は各プログラムの規約に従って利用してください。

### 新しい記事を追加する
1. `articles/sample-skincare.html` をコピーして `articles/新しい名前.html` を作る
2. タイトル・本文・商品（`review-box`）を書き換える
3. `articles.html` と `index.html` の記事カードをコピーして、新記事へのリンクを追加

### サイトの色を変える
`css/style.css` の先頭にある `:root { ... }` の色コードを変えるだけで全体の配色が変わります。

## 🚀 GitHub で公開する手順（GitHub Pages）

> このフォルダは git の準備まで済ませてあります。あとは GitHub にアップロードするだけです。

### A. GitHub CLI を使う場合（おすすめ・簡単）
1. [GitHub CLI](https://cli.github.com/) をインストール
2. ターミナルでこのフォルダに移動し：
   ```bash
   gh auth login
   gh repo create kaya-cosme --public --source=. --push
   ```
3. GitHub のリポジトリ → **Settings → Pages** で
   - Source: `Deploy from a branch`
   - Branch: `main` / `(root)` を選んで Save
4. 数分後 `https://<あなたのGitHubユーザー名>.github.io/kaya-cosme/` で公開されます 🎉

### B. ブラウザで手動アップロードする場合
1. GitHub にログイン → 右上「＋」→ **New repository**
2. リポジトリ名を `kaya-cosme` にして Create
3. 「uploading an existing file」から、このフォルダの中身を**すべて**ドラッグ＆ドロップ → Commit
4. 上記 A の手順3〜4 と同じく **Settings → Pages** で公開設定

## ⚠️ 公開前のチェックリスト
- [ ] `privacy.html` の連絡先・制定日を自分の情報に
- [ ] `about.html` のプロフィールを自分の言葉に
- [ ] アフィリリンク（`href="#"`）を実際のリンクに差し替え
- [ ] Amazonアソシエイト規約に沿った表記になっているか確認
