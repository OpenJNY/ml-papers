---
title: Pandoc と MathJax 用のプラグインを導入する
date: 2018-04-09 22:53:25
---

参考

 * [HexoのレンダリングエンジンとしてPandocを使う - Qiita](https://qiita.com/sky_y/items/7c29909c5cffa28b23d8)

# 手順

pandoc は必須

```sh
brew install pandoc
```

各種プラグインをインストール

```sh
npm install hexo-renderer-pandoc --save
npm install hexo-renderer-mathjax --save
```

デフォルトのレンダラが悪さをしてるので削除[^1]

[^1]: [更改Hexo的Markdown解析 | MicLee's Bolg](http://miclee.cn/2017/04/20/%E6%9B%B4%E6%94%B9Hexo%E7%9A%84Markdown%E8%A7%A3%E6%9E%90/)

```sh
npm uninstall hexo-renderer-marked --save
```

## mathjax サンプル

$\{ \mathbf{x}_n, t_n \}_{n = 1}^N$ に対して

$$
\mathbf{X} = \begin{pmatrix} \mathbf{x}_1^\top \\
\vdots \\
\mathbf{x}_N^\top \end{pmatrix}
$$

を計画行列と呼ぶ．

## pandoc のサンプル

[デモ](./pandoc-mathjax-test.html)