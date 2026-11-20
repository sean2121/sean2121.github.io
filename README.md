# CITRINE株式会社 紹介サイト

Jekyll で作っている。`main` に push すると GitHub Pages が自動でビルドして公開する。

## 記事を書く

1. `_posts/` に `YYYY-MM-DD-slug.md` という名前でファイルを作る（例: `_posts/2026-12-01-what-is-ontology.md`）。
   URL は `/articles/what-is-ontology/` になる。
2. 先頭に次のように書き、その下に Markdown で本文を書く。

   ```markdown
   ---
   title: "記事のタイトル"
   description: 一覧に出す要約（省略すると本文の冒頭が使われる）
   tags: [Ontology, 入門]
   ---

   本文……
   ```

3. push する。

- 書き方の見本は `_drafts/sample-article.md`。
- `_drafts/` に置いたファイルは公開されない。下書きはここに置き、公開するときに日付を付けて `_posts/` へ移す。
- 画像は `assets/images/` に置き、`![説明](/assets/images/xxx.png)` で貼る。
- 記事が1本もない間は、ナビの ARTICLES とトップページの新着欄は表示されない。
- 未来の日付の記事は、その日になるまで公開されない。

## ローカルで確認する

```sh
bundle install                    # 初回のみ
bundle exec jekyll serve --drafts # http://localhost:4000 （下書きも表示）
```

## ファイル構成

| 場所 | 内容 |
| --- | --- |
| `index.html` | トップページ。`<!-- TODO -->` の直後が差し替え箇所 |
| `articles/index.html` | 記事一覧 |
| `articles/tags.html` | タグ別一覧 |
| `_layouts/default.html` | 全ページ共通の枠（ヘッダー・フッター） |
| `_layouts/post.html` | 記事ページの枠 |
| `_includes/` | 記事リスト・タグの部品 |
| `assets/css/site.css` | スタイル（全ページ共通） |
| `_config.yml` | サイト名・著者名などの設定 |
