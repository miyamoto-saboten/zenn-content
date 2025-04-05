---
title: "作業メモ DaVinci Resolve Studioのカラースペース変換を用いて写真を加工する"
emoji: "🦔"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: [画像編集][DaVinci Resolve]
published: false
---

# 写真撮影に使用したカメラ
Sony α6400

# カラースペース変換の目的
各カメラメーカは独自のカラースペースを採用していたりする  
SonyでいうとS-GamutやS-Gamut3  
これを一般的なカラースペースに変換することで編集がしやすくなったり、異なるデバイスでの発色のばらつきを防いだりする

# 下準備
sonyのRAW画像は拡張子「.ARW」で保存されている  
このままではDaVinci Resolveで扱えないため[Adobe Digital Negative Converter](https://helpx.adobe.com/jp/camera-raw/using/adobe-dng-converter.html)
で変換をかける

# カラースペース変換の適用
1. カラータブへ移動
2. ライブラリにあるカラースペース変換をノードに対してドラッグアンドドロップ

## カラースペース変換設定項目
### 入力カラースペース、入力ガンマ
カメラ側の設定ここに入力する値が変わる  
Sony α6400では設定項目名は「ピクチャープロファイル」

