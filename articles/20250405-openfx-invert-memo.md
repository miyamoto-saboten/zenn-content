---
title: "メモ Openfxのinvert.cppについて処理の概要まとめ"
emoji: "💨"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [Openfx]
published: true
---

# ソースコードURL
[https://github.com/AcademySoftwareFoundation/openfx/blob/doc/Documentation/sources/Guide/Code/Example2/invert.cpp](https://github.com/AcademySoftwareFoundation/openfx/blob/doc/Documentation/sources/Guide/Code/Example2/invert.cpp)


# 用語の説明
## ホスト
プラグインを使用するアプリケーションのこと

例：DaVinci Resolve

## スイート
プラグインがホストの機能にアクセスする際に使用する、C言語で作られた構造体のこと

プラグインが直接ホストの内部関数を呼び出すことはできないため、スイートを通じて呼び出す

## プロパティ
ホストとプラグインが情報をやり取りする際に使用されるデータを「プロパティ」と呼ぶ

例：
- 画像のサイズ
- エフェクト名

## アクション
ホストがプラグインに対して処理を呼び出すことを「アクション」と呼ぶ


# 処理の流れ
## 1. プラグインの読み込み
以下の関数を実行することで、ホストがプラグインの情報を取得する：
- `OfxGetPlugin`
- `OfxGetNumberOfPlugins`

## 2. pluginMainの呼び出し
ホストが要求しているアクション名が`const char *action`に渡され、`strcmp` を用いて特定のアクション名と文字列比較を行い、処理を振り分ける

### onLoad
ここで必要なスイートを取得する

### describe
プラグインがサポートするピクセル深度、プラグインの名称、使用可能なコンテキスト（プラグインがどのような用途で使用されるか【例: フィルタリング、合成など】）などをプロパティに設定する

### describeInContext
コンテキストに応じたプラグインの動作を設定する

### render
画像処理を実行する


