---
title: GitHubリポジトリでZennのコンテンツを管理する
published: false
description: description
tags: Git, Zenn
---
## Zenn CLIのインストールとプロジェクトの作成
1. Zenn CLIのインストール
    Zenn CLIをインストールすると、ローカル環境で記事や本をプレビューしながら書くことができます。
    まずはnpm（Node.jsのパッケージマネージャ）を使用して、Zenn CLIをインストールします。
    ```bash
    npm install zenn-cli --global
    ```

2. 新しいZennプロジェクトの作成
    Zenn CLIを使って新しい記事を作成します。
    ```python
    zenn new:article
    ```
## GitHubのセットアップ
1. GitHubリポジトリの作成
   1. GitHubのサイトにアクセスし、ログインします。
   2. トップページの右上にある「＋」のアイコンをクリックして、「New repository」を選択します。
   3. リポジトリ名を入力します（例：zenn-contents）。この名前は任意ですが、zenn-contentsが推奨されています。
2. ZennプロジェクトをGitHubリポジトリにプッシュ
   1. 以下のコマンドでGitHubの新しいリポジトリをクローンします。
      ```bash
      git clone [GitHubリポジトリのURL]
      ```
   2. クローンしたリポジトリのディレクトリに移動し、Zennプロジェクトの内容をそのディレクトリにコピーします。
   3. 以下のコマンドで変更をGitにコミットし、GitHubリポジトリにプッシュします。
      ```bash
      git add .
      git commit -m "Initial commit"
      git push origin main
      ``` 
## 記事の編集と公開
1. VSCodeで記事の編集
   1. Visual Studio Code (VSCode)を開きます。
   2. 「File」>「Open」を選択し、先ほどクローンしたGitHubリポジトリを開きます。
   3. `articles`ディレクトリ内のMarkdownファイルを編集し、記事内容を書き込みます。 
2. 変更内容をGitHubにプッシュ
   1. VSCodeの左サイドバーからGitアイコンをクリックします。
   2. 変更をステージングし、コミットメッセージを入力した後、「✓」ボタンをクリックしてコミットします。
   3. 上部の「...」アイコンをクリックし、「Push」を選択して変更をGitHubにプッシュします。
3. ZennでのGitHub連携
   1. Zennのサイトにアクセスしてログインします。
   2. ダッシュボードから「GitHub連携」を選択します。
   3. 画面の指示に従い、GitHubとZennを連携させます。
4. Zennで記事を公開
   1. Zennのダッシュボードに移動します。
   2. 「記事」を選択し、公開したい記事の右側にある「公開する」ボタンをクリックします。
