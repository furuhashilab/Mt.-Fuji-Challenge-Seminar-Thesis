# satoaki-2024Seminar-shortpresentation
2024年度ゼミ論「」

青山学院大学 地球社会共生学部 地球社会共生学科

佐藤　愛妃 /　Aki Sato

学生番号 1A122083

指導教員 古橋大地 教授

©︎Furuhashi Laboratory/Aki Sato, CC BY 4.0

## Abstract
XYZタイルに標高データを加えて生成した3次元ボクセルとそれに紐づくユニークID（3次元空間ID）を管理するための空間インデックスライブラリを構築する。また、最終的にはUnited Nations Vector Tile Toolkit（UNVT）を用いたRaspberry Piへの実装を行う。特筆する点は、空間定義にポリゴンとして3次元ボクセルとボクセルに紐づいた3次元空間IDを使用する点である。これにより、従来の2次元地図やアナログ地図よりも詳細な地理空間データ管理とオフラインでの地図表示が可能となる。このプロジェクトでは、山岳地帯などの環境未整備かつ通信環境が整っていない場所での使用を想定している。その際、既存のUNVT-portableを参考に進めていきたい。

## Introduction
背景
地理情報システム（GIS）は、災害管理、都市計画、交通管理、農業、環境保護など、多くの分野で重要な役割を果たしている。特に、3次元空間情報は複雑な地形の分析や都市部での詳細な地図生成で重宝される。しかし、現実的な制約として、多くのGISは高コストであり、またオフラインでの利用が難しいという課題がある。本研究は、Raspberry Piという低コストのプラットフォームを使用し、UNVTを活用して効率的な3次元地理情報システムを構築することを目的としている。

目的
Raspberry Pi上で動作する3次元空間インデックスライブラリを構築し、低コストでの地理空間データ管理を実現する。
3次元ボクセルにユニークIDを生成し、データの正確な位置特定と管理を可能にする。
オフライン環境での実用性を高め、発展途上地域や災害時の応急対応における応用を目指す。
新規性
オフライン環境での地理空間データ管理: Raspberry Piを用いて、インターネット接続が不安定な環境でも高精度な地理情報を提供。
3次元ボクセルのユニークID生成: 3次元空間データの正確な管理とクエリを実現する新しいID生成アルゴリズムを導入。
統合された多層技術アプローチ: UNVT、GeoPandas、Scipy、SQLiteを組み合わせた統合的アプローチによるシステム構築。
このプロジェクトの新規性は、3次元空間ボクセルに紐づくユニークID（3次元空間ID）、Raspberry Pi（UNVT-portal）という低コストなハードウェアを利用することで、オフライン環境でも緯度経度に高さ情報を加えた高精度な地理情報処理を可能にできる点だ。3次元空間の基盤データを整備することは、エアモビリティや次世代ドローンなど広範な応用可能性を持ち、社会的な影響も大きい。

## Methods
使用するツールとその機能
1. United Nations Vector Tile Toolkit (UNVT)
機能: 地理空間データをベクトルタイルに変換し、オフライン環境でもデータを効率的に提供。ベクトルタイルは、データ量を抑えながら高い精度で地理情報を表示できる。
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
本プロジェクトにより、Raspberry Pi上で効率的な3次元空間インデックスライブラリを構築することができるようになる。これにより、オフライン環境でも高精度な地理情報の管理とクエリが可能になる。
3次元ボクセルにユニークIDを生成することにより、正確な位置特定とデータ管理が実現できる。
GPSモジュールとの統合により、リアルタイムの地理空間データの収集と可視化が可能になる。

## Discussion
### 利点
低コストでの実装: Raspberry Piの使用により、低予算で高性能な地理情報システムを構築できる。
オフライン機能: インターネットが利用できない環境でも、地理空間データを提供できる点が大きなメリットになる。
拡張性と応用範囲: 教育現場、災害対応、発展途上地域での活用が期待できる。
### 制限
ハードウェア制約: Raspberry Piの性能により、非常に大規模なデータセットではパフォーマンスが制限される可能性がある。
データ精度: GPSデータの精度が環境によって変動し、位置情報の正確性に影響を与える可能性がある。

## Conclusion
United Nations Vector Tile Toolkitを活用して、Raspberry Pi上で動作する3次元空間インデックスライブラリの構築を目指す。このシステムは、低コストでありながら高性能で、オフライン環境での地理情報提供を可能にする。災害対応、発展途上地域での利用、教育現場での実践など、多岐にわたる応用が期待できる。さらに、データ精度の向上とシステムの最適化により、より多くの実用的なニーズに応えることができる。

# 参考文献
- **タイトル**: *An Efficient Method for Offline Geospatial Data Processing Using Vector Tiles*
- **著者**: L. Zhang, H. Zhao
- **ジャーナル**: *International Journal of Geographical Information Science*
- **DOI**: [10.1080/13658816.2019.1583071](https://doi.org/10.1080/13658816.2019.1583071)

- **タイトル**: *Voxel-Based 3D Spatial Indexing for Efficient Geospatial Queries*
- **著者**: J. Smith, K. Johnson
- **ジャーナル**: *Computers, Environment and Urban Systems*
- **DOI**: [10.1016/j.compenvurbsys.2020.101469](https://doi.org/10.1016/j.compenvurbsys.2020.101469)