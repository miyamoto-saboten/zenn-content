---
title: "メモ Openfxのinvert.cppについてソースを読んで行く"
emoji: "💨"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [Openfx]
published: false
---

# リンク
[invert.cpp](https://github.com/AcademySoftwareFoundation/openfx/blob/doc/Documentation/sources/Guide/Code/Example2/invert.cpp)


# 使われる用語
## ホスト
プラグインを使うアプリケーションのこと

例：DaVinci Resolve

## スイート
プラグインがホストの機能にアクセスする際に用いるC言語で作られた構造体のこと

プラグインが直接ホストの内部関数を呼び出すことがはできないため、スイートを通じて呼び出す

## プロパティ
ホストとプラグインが情報をやり取りする際に用いられるデータのをプロパティと読んでいる

例
- 画像のサイズ
- エフェクト名

## アクション
ホストがプラグインに対して処理を呼び出すことをアクションと呼ぶ

