# satoaki-2024Seminar-shortpresentation
2024年度ゼミ論「United Nations Vector Tile Toolkit（UNVT）を用いた3次元空間インデックスライブラリの構築とRaspberry Piへの実装」

青山学院大学 地球社会共生学部 地球社会共生学科

佐藤　愛妃 /　Aki Sato

学生番号 1A122083

指導教員 古橋大地 教授

©︎Furuhashi Laboratory/Aki Sato, CC BY 4.0

## Abstract
このプロジェクトでは、United Nations Vector Tile Toolkit (UNVT)を使用して3次元ボクセルに紐づくユニークIDを生成する空間インデックスライブラリを構築し、Raspberry Piでの実装を行う。特筆する点は、空間定義にポリゴンとして3次元ボクセルとボクセルに紐づいた3次元空間IDを使用する点である。これにより、従来の2次元地図やアナログ地図よりも詳細な地理空間データ管理とオフラインでの地図表示が可能となる。このプロジェクトでは、山岳地帯などの環境未整備かつ通信環境が整っていない場所での使用を想定している。その際、既存のUNVT-portableを参考に進めていきたい。

## Introduction
Pythonライブラリで3次元空間IDの空間インデックスを構築

## Methods
使用するツールとその機能
1. United Nations Vector Tile Toolkit (UNVT)
機能: 地理空間データをベクトルタイルに変換し、オフライン環境でもデータを効率的に提供。
用途: ベクトルタイル生成、データの軽量化と最適化、オフライン地図の提供。
2. GeoPandas
機能: Pythonで地理空間データを操作し、データ解析や可視化をサポート。
用途: 地理空間データの前処理、解析、データフレーム形式での操作。
3. Scipy（cKDTree）
機能: 効率的な空間検索を可能にするデータ構造であるk-d treeを提供。
用途: 空間インデックスの構築とクエリ処理、近傍探索。
4. Raspberry Pi
機能: 小型コンピュータで、地理情報処理とオフライン地図システムのプラットフォームとして使用。
用途: 地図のローカル表示、GPSデータの取得と処理。
5. GPSモジュール
機能: リアルタイムでの位置情報を取得し、Raspberry Piでのデータ処理に利用。
用途: 現在地の特定、3D空間ボクセルの位置決定。
6. SQLite
機能: 軽量のSQLデータベースエンジンで、地理データのローカルストレージに利用。
用途: データベースの構築と管理、空間データのクエリ処理。
7. Node.js/NPM
機能: JavaScriptランタイム環境で、UNVTのインストールとタイル提供に使用。
用途: UNVTのインストールとサーバーの立ち上げ。

## Results

## Discussion

## Conclusion

# 参考文献
