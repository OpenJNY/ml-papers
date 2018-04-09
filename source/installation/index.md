---
title: Installation
date: 2018-04-09 22:53:25
---

hexo によるサイト構築

# GitHub Pages へのデプロイまで

## 必要なもの

* npm, git
* github アカウント

## 手順

まず hexo-cli のインストール

```sh
npm i -g hexo-cli
```

静的サイトのプロジェクトフォルダを作成し，デプロイに必要なモジュールをインストール．

```sh
hexo init ml-papers
cd ml-papers
npm install hexo-deployer-git --save
```

`_config.yml` を幾つか修正．

```yml
title: 機械学習の論文
subtitle:
description:
keywords:
author: OpenJNY
language: ja
timezone: Asia/Tokyo

# ...

# gh-pages のルートを指定する（io page なら不要）
url: https://openjny.github.io/ml-papers/
root: /ml-papers/

# ....

deploy:
  type: git
  repo: git@github.com:OpenJNY/ml-papers.git
  branch: gh-pages
```

デプロイ出来るか確認する．

```sh
hexo deploy -g
```

ソースコードは master ブランチで管理する．
この時勝手に public, node_modules あたりを無視する `.gitignore` が作成されるのでご安心を．

```sh
git init
git remote add origin git@github.com:OpenJNY/ml-papers.git
git add -A
git commit -m "first commit"
git push -u origin master
```

# pull して来た時

master ブランチだけとってきて，必要な node module をプロジェクト内にインストールすればよい．
```sh
git clone -b master git:github.com:openjny/ml-papers.git
cd ml-papers
npm install
```
