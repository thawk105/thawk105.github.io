---
layout: post
title: LaTeX の ref で図 ?? のようになってしまうエラー
---
### 執筆動機
日本語で解説しているサイトがすぐに見つからなかった．

### 問題
LaTeX を使用していて，正しいスペルで label と ref を入力しているのに，図?? となってしまう．

### 原因
main.log 等のログを閲覧してください．
そして，うまくいかなかった label や ref の名前でサーチしてください．
下記のようなログはありませんか？
>Package caption Warning: \label without proper reference on input line 6.
See the caption package documentation for explanation.
LaTeX Warning: Reference `fig:soft_arch' on page 9 undefined on input line 21.

これは label, ref の使い方が悪いことが原因です．

### 解決策
キャプションは図番号を更新するため，キャプションの前にラベルを挿入してはいけません，
・キャプションの中
・キャプションの後
いずれかにラベルを挿入すべきです．

ダメな例 :
>\label{hoge}
\caption{hoge}

良い例 :
>\caption{hoge}
\label{hoge}

### 参考
https://tex.stackexchange.com/questions/431676/problem-with-label-and-references-and-subfig-subcaption/431695

