---
title: Markdown記法で詰まる
date: 2017-01-29 20:04:18
tags:
- Hexo
- Markdown
---
コードの表示やコードの中の色変えるやつができなくてハマったけどやっとできた。

ただのコードだけなら、スペース４回かTab２回。

    <%- partial('post/date', {class_name: 'article-date', date_format: null}) %>

バッククオート( ` )3つで囲む法だと番号が付く。

```
<%- partial('post/date', {class_name: 'article-date', date_format: null}) %>
```

これで色がつかない！ってなって、やっと色付けられたやつが、
バッククオート( ` )3つのあとに「Javascript」をつける。

```Javascript
<%- partial('_partial/article', {post: page, index: false}) %>`
```

ちなみにさっきから言ってるこの「色」は「シンタックスハイライト」と言う。
覚えた。

MarkdownについてはQiitaにたくさんあるので参考サイトは割愛。
