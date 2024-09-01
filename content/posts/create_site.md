+++
title = 'サイトを作ったときの備忘録'
date = 2024-08-30T08:07:43+09:00
draft = false
+++
## 何を使ったか
このサイトは次の３つやつらを使って作った．
- [Hugo](https://gohugo.io/)  
> Hugoは静的サイトジェネレーターと呼ばれるツールの1つで、Go 言語で開発された高速なHTMLサイト作成ツールです。マークダウンファイルからサイトを生成できるため、ブログやドキュメントサイト構築に最適です。[^1]
[^1]: https://jitera.com/ja/insights/18138 より引用．
- [Blowfish](https://blowfish.page/ja/)  
これは Hugo で使えるテンプレの１つ．ドキュメントもしっかりしてて使いやすそうだったので採用．
- [GitHub](https://github.co.jp/)  
これ自体については以下の通り．
> GitHub はソフトウェア開発のプラットフォームとして広く使われている、アメリカの同名の企業が提供しているサービスです。利用者はプログラムのソースコードをアップロードし、複数のユーザーと共有して共同作業を行ったり、ソフトウェア開発プロジェクトを管理したりすることができます。[^2]
[^2]: https://www.ntt.com/bizon/glossary/e-g/GitHub.html より引用．

ページのホストも GitHub Pages というやつを使っている．
詳しくは後ほど．

## 手順
サイトを作る手順は次の通り．
1. **ローカルで Hugo + Blowfish を用いてサイト公開のためのいろいろなファイルを作成**  
これについては Blowfish のドキュメントをみれば大体わかる．Hugo自体の知識もほとんどいらない．少し詰まった部分もあるが，それは後ほど語る．
2. **ローカル環境のフォルダと GitHub のレポジトリを同期**  
    1. GitHub のインストールについては https://www.curict.com/item/60/60bfe0e.html などを参照．Git というものをインストールして，その後 GitHub のサイトに行きアカウント作成．
    2. ローカルのフォルダと GitHub のレポジトリの間の同期については https://www.kagoya.jp/howto/rentalserver/webtrend/vscode/ を参照．
3. **GitHub Pages を用いてレポジトリのサイトファイルをいい感じに公開**  
これについては Hugo の公式ドキュメント https://gohugo.io/hosting-and-deployment/hosting-on-GitHub/ を参照．

## 詰まったところ
### Blowfishまわり
基本的にはドキュメント通りに進めれば問題ないが，以下の点に注意．
- **日本語でサイトを作る場合**  
このときドキュメント通りに進めると，ファイル名やとあるファイルの中の「En, en」を「Ja, ja」に置き換えるところがある．ところが，ドキュメントに載っているファイル以外にも「en」がある場合があるので注意．
- **ファビコンの変更方法**  
ファビコンの変更方法は公式ドキュメントにあるが，それだけでは不十分．公式ドキュメントの作業終了後，`themes\blowfish\loyouts\partials\` にある `head.html` を `layouts\parials\` 内にコピーし，このサイト https://stackoverflow.com/questions/67662582/hugo-site-favicon-shows-locally-but-cannot-be-found-in-deployment にあるように，`head.html` の中身の
```
<link rel="icon" type="image/png" sizes="32x32" href="{{ "/img/favicon-32x32.png" | relURL }}">
<link rel="icon" type="image/png" sizes="16x16" href="{{ "/img/favicon-16x16.png" | relURL }}">
<link rel="apple-touch-icon" sizes="180x180" href="{{ "/img/apple-touch-icon.png" | relURL }}">
```
みたいな部分を
```
<link ... href="./img/favicon-32x32.png">
<link ... href="./img/favicon-16x16.png">
<link ... href="./img/apple-touch-icon.png">
```
に修正すればよい．
元サイトでは
```
<link ... href="/img/favicon-32x32.png">
<link ... href="/img/favicon-16x16.png">
<link ... href="/img/apple-touch-icon.png">
```
になっているが，`/img`ではなく`./img`じゃないとダメっぽい．
### Hugoまわり
- **数式の改行の話**  
数式は Blowfish により KaTex を用いて記述できるようだが，`align` 環境での改行の挙動が少しおかしいので，Hugo の自体を KaTex に対応させるのが無難だと思われる．今回は Hugo の公式ドキュメント https://gohugo.io/content-management/mathematics/ と https://kuroyei.com/blog/2024/hugo_katex_no_break_lines_issue/ の通りに設定してうまくいった．

- **大小記号のはなし**  
大小関係 `<`,`>` をそのまま使うとうまく表示されない場合がある．
`\lt`, `\gt`を使おう．

- **日付表示の話**  
これは Hugo が悪いのだが，日付設定のフォーマットが信じられない．
詳しくは https://ytyaru.hatenablog.com/entry/2022/10/31/000000 を見てくれ．