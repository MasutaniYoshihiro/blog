---
layout: post
title:  jekyllにサイトマップを追加する方法【jekyll-sitemap】
date:   2022-05-02 06:11:25 +0900
categories: jekyll
tag: article
---

## 手順

1. Gemにjekyll-sitemapを追加
2. _config.ymlにjekyll-sitemapを追加
3. 除外ページ設定
4. ビルド

### 1.Gemにjekyll-sitemapを追加
Gemfileに追加
```gemfile
gem 'jekyll-sitemap'
```

### 2._config.ymlにjekyll-sitemapを追加
プラグインに追加
```yml
plugins:
  - jekyll-sitemap
```

### 3.除外コンテンツの設定
FrontMatter(https://jekyllrb-ja.github.io/docs/front-matter/)に追加する場合
```markdown
sitemap: false
```

FrontMatterが使用できないコンテンツに関しては、_config.ymlで設定するします。
```yml
defaults:
  -
    scope:
      path: "assets/**/*.pdf"
    values:
      sitemap: false
```

### 4.ビルド
最後にjekyll buildすればsitemap.xmlが生成されていることが確認できると思います。<br>
robots.txtはクローラにサイトマップの位置などを指示するファイルです。こちらも自動生成してくれます。
```
root
|-- _site
|   |-- sitemap.xml
|   |-- robots.txt
```