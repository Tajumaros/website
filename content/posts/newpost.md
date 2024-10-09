+++
title = '【雑記】新しい記事の作り方'
date = 2024-10-09T19:05:07+09:00
draft = false
tags = ['ホムペ関連']
+++
## hugoで新しい記事を作成する方法
たとえば
```
hugo new posts/newpost.md
```
とターミナルに書けば，`./content/posts`内にnewpostという名前で
```
+++
title = 'newpost'
date = 2024-10-09T19:05:07+09:00
draft = true
+++
```
みたいなmarkdownファイルが作られる．

この最初のテンプレを編集することもできる．
詳しくは https://qiita.com/n0bisuke/items/4701481c3bca4df81b0b を参照してほしい．

なお，
```
hugo
```
で **ビルドするのを忘れずに** ．

## VSCでの記事のプレビュー
vscの拡張機能 Markdown Preview Enhanced がインストールされていれば，`ctrl+k`を押した後`v`で横にプレビュー画面が出る．