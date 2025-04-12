---
title: "メモ Openfxのinvert.cppについてソースを読んで行く"
emoji: "💨"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [Openfx]
published: false
---

# URL
[https://github.com/AcademySoftwareFoundation/openfx/blob/doc/Documentation/sources/Guide/Code/Example2/invert.cpp](https://github.com/AcademySoftwareFoundation/openfx/blob/doc/Documentation/sources/Guide/Code/Example2/invert.cpp)


# 使われる用語
## ホスト
プラグインを使うアプリケーションのこと

例：DaVinci Resolve

## スイート
プラグインがホストの機能にアクセスする際に用いるC言語で作られた構造体のこと

プラグインが直接ホストの内部関数を呼び出すことがはできないため、スイートを通じて呼び出す

## プロパティ
ホストとプラグインが情報をやり取りする際に用いられるデータをプロパティと読んでいる

例
- 画像のサイズ
- エフェクト名

## アクション
ホストがプラグインに対して処理を呼び出すことをアクションと呼ぶ


# 処理の流れ
## 1.プラグインの読み込み
関数
- OfxGetPlugin
- OfxGetNumberOfPlugins 
の実行によりホストがプラグインの情報を取得する


## 2. pluginMainの呼び出し
`const char *action`内にホストから送信されるアクション名が入っているため、strcmpを用いて特定のアクション名と文字列比較をし処理を振り分けている

### onLoad
ここで必要なスイートを取得している
### describe
プラグインがサポートするピクセル深度、ラベル、グループ、使用可能なコンテキストなどをプロパティへ設定
### describeInContext
コンテキスト（プラグインがどのような状況や用途で使用されるか　例: フィルタリング、合成など）でのプラグインの動作を設定する
### render
画像処理を実行する


