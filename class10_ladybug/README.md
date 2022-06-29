### デザインエンジニアリング特論第10回 Ladybug&Honeybee

#### Ladybug & Honeybeeとは？

#### テーマ : オーダー感をおさえる  

[説明ページ](https://www.ladybug.tools/)

0. 環境構築について\
   [こちらのwebサイト](https://walk-thru-sustainable-living.com/ladybug-tools-install/)がよくまとまっているので、こちらを参照しながら環境を構築してください。\
   環境構築してもらってる間に先週途中だった話をしたいと思います。

1. 積算日射量の計算について\
   [building-envのサイト](https://building-env.com/archives/573)からGrasshopperコンポーネントをダウンロードし、開きます。

単純に言えば、夏は受熱日射量を最小化し、冬は受熱日射量を最大化する。\
じゃあ冬にどれくらいの日射量が必要か数字のオーダー感わかりますか？

演習. 建物における熱取得、熱損失の必要量に比べて、多いのか少ないのか考える

プログラム（オフィス、住宅 etc)にもよるが、建物の熱負荷は以下の通り\
![BAUES Analysis](img/heat_balance.png)

熱取得

- 窓からの熱取得
- 壁体伝熱による熱取得
- 照明発熱
- 人体発熱
- OA機器による発熱

熱損失

- 窓からの熱損失
- 壁体伝熱による熱損失

=>冷房期であれば、熱取得>熱損失の状況により室温が高くなりすぎて、冷房需要が発生する\
=>暖房期であれば、熱損失>熱取得の状況により室温が低くなりすぎて、暖房需要が発生する\
(わかりやすくするために環境工学の厳密性からすると突っ込みどころがあるのは容赦ください)

[川島先生の本](https://www.amazon.co.jp/%E7%92%B0%E5%A2%83%E3%82%B7%E3%83%9F%E3%83%A5%E3%83%AC%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3%E5%BB%BA%E7%AF%89%E3%83%87%E3%82%B6%E3%82%A4%E3%83%B3%E5%AE%9F%E8%B7%B5%E3%82%AC%E3%82%A4%E3%83%89%E3%83%96%E3%83%83%E3%82%AF-%E5%B7%9D%E5%B3%B6-%E7%AF%84%E4%B9%85/dp/4395321445)を例として説明すると、

step1. 暖房需要がどれくらいだったかを推定する\
![エネルギー消費量実測値内訳](img/measure.png)\  
暖房の一次エネルギー消費量9.7GJ -> エアコンによる消費エネルギー973kWh ->運転COP3と仮定->暖房によって補った熱量約3000kWh

step2. 窓からの日射熱取得がどれくらいだったかを推定する\  
![直達日射量](img/heat_gain.png)\  
南窓からの日射熱取得\
2階部分 300kWh/m2×0.59(SHGC)×12m2(窓面積)×0.8(サッシ分考慮)=1,700kWh\
1階部分 180kWh×0.59(SHGC)×14m2(窓面積)×0.8(サッシ分考慮)=1,190kWh 合計 約3000kWh

step3. 結論\
暖房期の必要熱量だけで考えると、窓からの日射熱取得がなければ3000+3000=6000kWhの熱量が必要だった。 その半分の熱量が窓からの日射熱取得\
(厳密には昼取得した熱を暖房が必要な夜に蓄熱しないといけなかったりするので単純な話ではない)\
=>ここのオーダー感を見誤って、単純に高断熱で冬の取得日射を最大化すると、冬の期間でもオーバーヒートしてしまったりするので要注意\
しかも夏の期間は窓が大きい分だけ冷房負荷を増やしてしまう => ケースバイケースの最適化問題

統計データと比較すると、夏の冷房エネルギー消費量が割合的に多め？\
参照. ![エネルギー消費量の統計データ](img/statistics.png)

参照. [一次エネルギーへの換算](https://j-net21.smrj.go.jp/development/energyeff/Q1258.html)

補足.
[一次エネルギー、二次エネルギー](https://j-net21.smrj.go.jp/development/energyeff/Q1183.html#:~:text=%E3%80%8C%E4%B8%80%E6%AC%A1%E3%82%A8%E3%83%8D%E3%83%AB%E3%82%AE%E3%83%BC%E3%80%8D%E3%81%A8%E3%81%AF%E3%80%81,%E3%81%AE%E7%B7%8F%E9%87%8F%E3%82%92%E6%8C%87%E3%81%97%E3%81%BE%E3%81%99%E3%80%82)

2. 太陽光発電システムの計算について\
   [building-envのサイト](https://building-env.com/archives/76)からGrasshopperコンポーネントをダウンロードし、開きます。

注意)Rhinocerosの単位をmにしてから開いてください。

演習. 身の回りの電力需要を満たすために必要なPV容量を考えてみよう Q. エアコンの消費電力は?

例.
[家庭用ダイキンエアコン](https://ec.daikinaircon.com/iportal/CatalogViewInterfaceStartUpAction.do?catalogId=CR21349B-2&itemNumber=&designID=3)

Q. EVのバッテリーを満タンにするのに必要なPVの枚数、時間は？

例. [Tesla](https://evsmart.net/carMaker/Tesla/Model3/)

Q. PV1kW分(大体4-5枚分くらい)が年間で発電できる電力は？

A. [東京大学前准教授の記事](https://president.jp/articles/-/58676?page=7)

Q. メガソーラーの発電容量と他の発電所の能力を比較

A.
[メガソーラーランキング](https://project.nikkeibp.co.jp/ms/atcl/19/feature/00007/00023/?ST=msb)

[1位のメガソーラー詳細](https://project.nikkeibp.co.jp/ms/atcl/19/feature/00001/00053/?ST=msb)

[火力発電所マップ](http://agora.ex.nii.ac.jp/earthquake/201103-eastjapan/energy/electrical-japan/type/1.html.ja)

[横須賀パワーステーション](https://www.pref.kanagawa.jp/docs/ap4/cnt/f247/p363866.html)

Q. 再生可能エネルギーの可能性?

A. [東京大学前准教授の記事](https://president.jp/articles/-/58676)  

課題について  
設計課題と絡めて、「こういうことやりたい」っていうのがあったら、それを一緒に実装してそれで課題提出っていう方向もあり