# CI/CD職務経歴書テンプレート

GitHub ActionsでのPDF自動生成に対応したITエンジニア向け職務経歴書テンプレート


## 導入

```bash
$ npm install
```


## 記法

基本的に [Markdown](https://docs.github.com/ja/github/writing-on-github/basic-writing-and-formatting-syntax) に準拠

- 改行
  - 2文字以上の連続した半角スペース
- 右揃え
  - `> {text}`
  - 引用 (backquote) の構文だが、CSSによりPDF出力時は「右揃え」になる
- 改ページ
  - `<div style="page-break-before:always"></div>`
  - Markdown 内に上記 HTML コードを直接記述する


## 校正チェック

`-s` オプションで、校正チェックによるエラーをログ出力しない

```bash
$ npm run lint -s
```


## PDF出力（開発環境）

```bash
$ npm run build
```


## PDF出力（GitHub Actions）

`v*` タグ（`*` は任意のバージョン番号）を付けて commit & push する

```bash
$ git commit -m "(sample) add job"
$ git tag v1.0
$ git push origin --tags
```


## 開発モード

Chronium 上で HTML プレビュー表示と開発者ツールが起動する（CSS や configファイルの調整用）

```bash
$ md-to-pdf ./resume.md --devtools --config-file ./config.json
```

- `Ctrl+C` で終了


## 参考

- [エンジニアが読みたくなる職務経歴書 - dwango on GitHub](https://dwango.github.io/articles/engineers-resume/)
- [GitHubの機能をフルに使って職務経歴書の継続的インテグレーションを実現する：ryo_kawamata - Zenn](https://zenn.dev/ryo_kawamata/articles/resume-on-github)


## 使用フォント

- 源ノ角ゴシック (Source Han Sans)
  - https://github.com/adobe-fonts/source-han-sans
- 白源 (HackGen)
  - https://github.com/yuru7/HackGen
