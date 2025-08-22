# VibePrompt Studio

## 概要

`VibePrompt Studio` は、AI向けのプロンプト作成を効率化するために設計された、ローカル環境で動作するシングルHTMLファイルのMarkdownエディタです。
Windows 95風の懐かしいレトロなUIデザインと、モダンなプロンプトエンジニアリング支援機能を融合させています。

サーバー不要で、ブラウザだけで動作するため、手軽に利用を開始できます。

## 主な機能

- **2ペインUI**: 左側にMarkdown入力、右側に最終的なプロンプトのMarkdownプレビューを配置した、直感的なインターフェース。
- **Markdownエディタ**: [CodeMirror](https://codemirror.net/)をベースにした高機能エディタを搭載。
  - シンタックスハイライト
  - 行番号表示
  - 自動ブラケット補完
- **入力補助ツールバー**: ボタンをクリックするだけで、太字、見出し、リスト、リンクなどのMarkdown記法を簡単に入力できます。
- **リアルタイムプレビュー**: 入力されたMarkdownは、YAMLフロントマター（`---`で囲まれた部分）を解釈し、システムプロンプトなどと結合された上で、最終的なプロンプトとして右側のペインにMarkdown形式でリアルタイム表示されます。
- **トークン数カウンター**: [js-tiktoken](https://github.com/dqbd/js-tiktoken)を利用し、OpenAIの`cl100k_base`モデルに基づいたトークン数をリアルタイムで計算・表示します。
- **テンプレート機能**: 「コード生成」「要約」など、一般的なタスクのプロンプトテンプレートをワンボタンで挿入できます。
- **ファイル操作**: 作成したプロンプトは、Markdown形式（`.md`）または設定を含むJSON形式（`.json`）でローカルに保存できます。また、既存のファイルを読み込んで編集を再開することも可能です。
- **ローカル完結**: すべての処理はブラウザ内で完結します。編集内容が外部に送信されることはありません。（※ライブラリはCDN経由で読み込まれます）

## 使い方

1.  リポジトリにある `vibe_prompt_studio_ローカル_1_ファイル版（プロトタイプ）.html` ファイルをダウンロードします。
2.  そのファイルをGoogle ChromeやFirefoxなどのモダンなWebブラウザで開きます。

これだけでエディタが起動します。サーバーを立てる必要はありません。

## 技術スタック

本ツールは、以下のライブラリを活用して構築されています。

- **HTML / CSS / JavaScript** (Vanilla)
- **[CodeMirror](https://codemirror.net/)**: エディタ機能
- **[Split.js](https://split.js.org/)**: ペイン分割レイアウト
- **[marked.js](https://marked.js.org/)**: MarkdownからHTMLへの変換
- **[DOMPurify](https://github.com/cure53/DOMPurify)**: HTMLサニタイズ
- **[js-yaml](https://github.com/nodeca/js-yaml)**: YAMLフロントマターの解析
- **[js-tiktoken](https://github.com/dqbd/js-tiktoken)**: トークン数の計算