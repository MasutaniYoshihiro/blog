---
layout: post
title:  KMarkdown
date:   2022-07-09 15:57:00 +0900
categories: jekyll
tag: article
---

よく使うはずのやつを覚え書き！

## ヘッダー（hタグ）

~~~
# H1 header
## H2 header
### H3 header
#### H4 header
##### H5 header
###### H6 header
~~~

# H1 header
## H2 header
### H3 header
#### H4 header
##### H5 header
###### H6 header

## 引用（Blockquotes）
***ソースコード***
~~~
> Jekyllは、個人、プロジェクト又は組織のサイト向けの、簡単で、ブログのような静的サイトジェネレーター（英語版）である。
> GitHubの共同創業者であるトム・プレストン・ワーナー（英語版）によって開発が開始され、Rubyで記述されており、自由ソフトウェアライセンスのMIT Licenseの条件に基づいて配布されている。
>
> > Jekyllは、個人、プロジェクト又は組織のサイト向けの、簡単で、ブログのような静的サイトジェネレーター（英語版）である。
> > GitHubの共同創業者であるトム・プレストン・ワーナー（英語版）によって開発が開始され、Rubyで記述されており、自由ソフトウェアライセンスのMIT Licenseの条件に基づいて配布されている。
>
> ### ヘッダーとかも書ける
~~~
***実例***
> Jekyllは、個人、プロジェクト又は組織のサイト向けの、簡単で、ブログのような静的サイトジェネレーター（英語版）である。
> GitHubの共同創業者であるトム・プレストン・ワーナー（英語版）によって開発が開始され、Rubyで記述されており、自由ソフトウェアライセンスのMIT Licenseの条件に基づいて配布されている。
>
> ### ヘッダーとかも書ける
> > Jekyllは、個人、プロジェクト又は組織のサイト向けの、簡単で、ブログのような静的サイトジェネレーター（英語版）である。
> > GitHubの共同創業者であるトム・プレストン・ワーナー（英語版）によって開発が開始され、Rubyで記述されており、自由ソフトウェアライセンスのMIT Licenseの条件に基づいて配布されている。
>

## コードブロック
***ソースコード***
~~~~~~~~~
~~~~~~
~を3つ以上つなげて囲む
~~~
初回出現以上の~出現行でクローズされる
~~~~~~~~
~~~~~~~~~~

***実例***
~~~~~~
~を3つ以上つなげて囲む
~~~
初回出現以上の~出現行でクローズされる
~~~~~~~~

***ソースコード***
~~~~~~
~~~ ruby
def who?
  puts "jekyll!"
  # 言語を開始行の末尾に入れるとハイライトしてくれる
end
~~~
~~~~~~

***実例***
~~~ ruby
def who?
  puts "jekyll!"
  # 言語を開始行の末尾に入れるとハイライトしてくれる
end
~~~

## 行区切り

***ソースコード（書き方はいろいろある）***
~~~
* * *
~~~

***実例***
* * *

↑これ


## リスト

***ソースコード***
~~~
1. This is a list item
2. And another item
2. And the third one
   with additional text
~~~

***実例***
1. This is a list item
2. And another item
2. And the third one
   with additional text

***ソースコード***
~~~
* A list item
with additional text
~~~

***実例***
* A list item
with additional text

***ソースコード***
~~~
1.  This is a list item

    > with a blockquote

    # And a header

2.  Followed by another item
~~~

***実例***
1.  This is a list item

    > with a blockquote

    # And a header

2.  Followed by another item

***ソースコード***
~~~
1. Item one
   1. sub item one
   2. sub item two
   3. sub item three
2. Item two
~~~

***実例***
1. Item one
   1. sub item one
   2. sub item two
   3. sub item three
2. Item two

## Extensions
***ソースコード***
~~~
これは私が
{::comment}
（ここで一息つく）
{:/comment}
... まだ小さいときにあった本当の話です。

後ろを振り向くと
そこには {::nomarkdown}**白く血の引いた女の顔が**{:/}!
~~~

***実例***

これは私が
{::comment}
（ここで一息つく）
{:/comment}
... まだ小さいときにあった本当の話です。

後ろを振り向くと
そこには {::nomarkdown}**白く血の引いた女の顔が**{:/}!

## リンク

***ソースコード***

~~~
詳しく見るには [ここ](http://example.com)
をクリックしてください！
~~~

***実例***

詳しく見るには [ここ](http://example.com)
をクリックしてください！

## 画像リンク

***ソースコード***

画像はフォルダを作成して入れておく。

絶対パス（/img/sample_image.png）の場合はディレクトリ直下からの絶対パスの場所に、

相対パス（img/sample_image.png）の場合は記事パスの直下に作成する必要がある。
~~~
サンプル画像だよ: ![サンプルの画像](/img/sample_image.png)
~~~

***実例***

サンプル画像だよ: ![サンプルの画像](/img/sample_image.png)

## テーブル

***ソースコード***
~~~
| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}
~~~

***実例***

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}

## ブロック属性
***ソースコード***
~~~
> ブロックにtitleが付与される
{: title="Blockquote title"}
~~~

***実例***
> ブロックにtitleが付与される
{: title="Blockquote title"}

***ソースコード***
~~~
> クラスを付与したりできる
{: .class1 .class2}
~~~

***実例***
> クラスを付与したりできる
{: .class1 .class2}


### 参考
https://kramdown.gettalong.org/quickref.html