---
title: Hexo と Github Pages で作ったよ
date: 2017-01-29 13:01:35
tags:
- Hexo
- Github Pages
---
先程Aboutページをやっと作り終えまして、さっそく忘れないようにﾒﾓφ(｀д´)φﾒﾓ

ブログ、人生二回目になります。
前回は前やってたサイトの日記代わりで書いてて、独自ドメインも持ってたのでMovableTypeからのWordPressを使っていました。

ところがなんでかWordPressの設定画面がぶっこわれちゃって、PHPいろいろいじったりMySQLいじったりいろいろやってみたけど結局直せなくてやめちゃった。

今回はなんでこの環境にしようとしたかというと、WordPressするには鯖関係めんどいし重い、はてぶだと楽すぎ、新しく自分で環境構築したい、などの理由があげられます。

HexoにしたのはJavaScriptだから。

ぐぐって先駆者さんたちの知恵を拝借、設置自体はとてもカンタンでした〜

---
<h3>設置</h3>

なんだかんだこちらにお世話になる。
<a href="https://liginc.co.jp/web/programming/server/104594" target="_blank">所要時間3分!? Github PagesとHEXOで爆速ブログ構築してみよう！</a>


<h3>拡張</h3>

__Aboutmeページ作る。__

<pre>$ hexo new page about-me</pre>

__ヘッダにリンク貼る。__

/themes/landscape/_config.ymlの設定

<pre>
# Header
  menu:
    Home: /
    Archives: /archives
    About me: /about-me/
  rss: /atom.xml
</pre>

__日付とシェアリンクとる__

/themes/landscape/layout/_partial/article.ejs
をコピーし、
/themes/landscape/layout/_partial/article-page.ejs
を作成。

参考サイトさんでは４行目としていましたが、私のarticle.ejsは３行目にあった

    <%- partial('post/date', {class_name: 'article-date', date_format: null}) %>

と、２６行目〜３０行目

    <a data-url="<%- post.permalink %>"
    〜
    <%- partial('post/tag') %>

を削除。

/themes/landscape/layout/page.ejsの

~~~Javascript
<%- partial('_partial/article', {post: page, index: false}) %>
~~~

を

~~~Javascript
<%- partial('_partial/article-page', {post: page, index: false}) %>
~~~
に変更。

参考
<a href="http://code-ur-life.blogspot.jp/2016/01/hexo.html" target="_blank">Hexoでのリンクの設定</a>
<a href="http://pagent.github.io/2014/11/29/page-no-date/" target="_blank">Hexoの固定ページを日付け無しに</a>
