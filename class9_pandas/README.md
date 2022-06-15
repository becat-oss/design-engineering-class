### デザインエンジニアリング特論第9回 ClimateConsultant Pandas  

#### climate consultantとは?  
気象データを可視化するツールです。Ladybug&HoneybeeやclimateStudioで使われている湿り空気線図上の快適線プロットやヒートマップなどのビジュアルの元祖はここじゃないかと勝手に思っています。  
[webサイト](https://www.sbse.org/resources/climate-consultant)からOSにあわせてインストーラをダウンロードしてください  

#### jupyter notebookを用いて、Python、pandasを使ってみる    
1. 以下のフォルダに移動  
```
design-engineering-class/class9_pandas
```  
2. Pythonの環境を設定する  
2-1. Anacondaをインストールする  
Anacondaとはデータ分析、機械学習などに必要なライブラリをパッケージしたソフトウェアです。  
[webサイト](https://www.anaconda.com/products/distribution)からパッケージをインストールします。     

インストールの手順は[こちらのwebサイト](https://www.python.jp/install/anaconda/windows/install.html)を参照します。  

2-2. Anaconda Promptを開く  
アプリケーションからAnaconda promptを開きます  

2-3. 以下のコマンドで今回のデモ用の環境を構築する  
```
conda create -n class9_pandas --file pandas_env.txt
``` 

2-4. 以下のコマンドで2-3で作成した環境に入る  
```
activate class9_pandas
``` 

3. jupyter notebookを以下のコマンドで起動  
```
jupyter notebook
``` 





