---
title: "作業メモ WindowsでOpenfxプラグインをビルドする"
emoji: "👣"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [Openfx]
published: true
---

## 作業環境
Widows11

# 大目標
[build-cmake.sh](https://github.com/AcademySoftwareFoundation/openfx/blob/main/install.md#standard-builds)を実行できるようにする

## 中目標
1. シェルスクリプトを実行できるようにする
git bashのインストール

2. cmakeコマンドが実行できるにする
cmakeのインストール

3. conanコマンドが実行できるようにする
    1. python3のインストール
    2. pipでconanをインストール
    3. インストールされたディレクトリへパスを通す

環境変数CONAN_HOMEでパッケージの保存先が指定できる

## build-cmake.shが実行できたら
下記ディレクトリ配下に「example-Basic.ofx.bundle」といったディレクトリができる
C:\Program Files\Common Files\OFX\Plugins\OpenFX Examples

ここに入っているプラグインはDaVinci Resolveで認識されることを確認

