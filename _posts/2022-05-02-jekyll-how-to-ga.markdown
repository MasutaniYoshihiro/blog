---
layout: post
title:  jekyllにGoogleAnalyticsを設定する方法
date:   2022-05-02 06:11:25 +0900
categories: jekyll
tag: article
---

## 概要

1. google-analytics.htmlを作成
2. ヘッダーに追加
3. _config.ymlにidを追加
4. ビルド

## 手順
### 1.google-analytics.htmlを作成
_includesディレクトリにgoogle-analytics.htmlを作成し以下のコードを貼り付けます。
```html
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id={{site.google_analytics}}"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', '{{site.google_analytics}}');
</script>
```

### 2.ヘッダーに記載を追加
ヘッダーを定義しているhtmlに記述を追加します。<br>
例えば、_include/head.html<br>
※ご自身の環境に一致するファイルに読み替えてください。
```markdown
{% raw %}
<head>
  :
  {% if jekyll.environment == 'production' and site.google_analytics %}
    {% include google-analytics.html %}
  {% endif %}
  :
</head>
{% endraw %}
```

### 3._config.ymlにidを追加
GoogleAnalyticsのプロパティのデータストリームごとに発行される「測定ID」です。
```markdown
google_analytics: G-**********
```

### 4.ビルド
本番環境でビルド
```bash
JEKYLL_ENV=production bundle exec jekyll build
```

ブラウザで表示されたページのソースを見ると、headタグ内にgoogle-analytics.htmlの内容が存在しているはずです。