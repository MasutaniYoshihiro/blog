---
layout: post
title:  "RubyのインストールからローカルでJekyllのサイトを実行するまで"
date:   2022-04-29 15:11:25 +0900
categories: jekyll update
tag: article
---

## Jekyllってなに？
静的サイトジェネレーター<br>
 → 特定のルールに従って記述されたテキストとかをHTMLとして生成するツール

このセクションの記述はこんな感じ。
```
## Jekyllってなに？
静的サイトジェネレーター
:
:
```



## 環境準備

1. rbenvインストール
2. Rubyインストール
3. Jekyllインストール

### 1.rbenvインストール
```bash
# Homebrewで`rbenv`と`ruby-build`をインストール
brew install rbenv ruby-build

# rbenvの設定を反映
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
source ~/.bash_profile

# （zshの場合はこっち）
# echo 'eval "$(rbenv init -)"' >>  ~/.zshrc
# source ~/.zshrc
```

### 2.Rubyインストール
```bash
# Rubyのバージョンを確認
rbenv install --list

# Rubyをインストール（時間かかる）
rbenv install 2.7.4

# 使用するRubyバージョンを設定
rbenv global 2.6.5

# Rubyバージョンを確認
ruby --version
```

### 3.jekyllインストール
```bash
gem install jekyll

# jekyllを使うのに必要なのでbundlerもインストール
gem install bundler
```

ここまでで準備はおしまい。

## Jekyllでサイトを作る
※本家のやつそのままの手順

ユーザーディレクトリにmyblogというブログを作る。

```bash
cd ~
jekyll new myblog
```

これだけでjekyllのブログが出来上がる。

次に、myblogディレクトリに移動して、ローカルでサーバーを起動。

ブラウザから[http://localhost:4000](http://localhost:4000)でアクセスできる。

```bash
cd myblog
bundle exec jekyll serve
```

ctrl-c で停止できる。
