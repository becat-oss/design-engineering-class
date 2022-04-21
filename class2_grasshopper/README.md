## （余裕ある人は）予習資料  
[ghPythonに関する説明](https://developer.rhino3d.com/guides/rhinopython/your-first-python-script-in-grasshopper/)
Grasshopper上でpythonを使うための説明が書いてあります。英語の練習だと思って読んでいくと力になること間違いなし。

## Grasshopperに関する質問  
#### Q. GraftとFlattenの理解が困難に感じました。GraftやFlattenをしてないと成立しない例を見てみたいです。  

#### A. Grasshopperで扱うデータの型の種類とデータツリーについて説明した後に、データツリーの構造を変える(GraftやFlattenなど)必要があるケースを説明します。  

#### Q. ルーバーなどをデザインする際にはGHはかなり強力だなと感じました。実際の設計ではパラメトリックツールが得意な場面と苦手な場面があると思うのですが、どのように使い分けられていましたか?  

#### A. 以下の条件にあてはまるときにパラメトリックツールを使っていました。  
- 感度分析(sensitivity analysis)を行って設計者にどのパラメータが大事かを伝えたいとき  
- 要件を聞いて、パラメータと目的変数が明確に定義できる場合（意外とできない場合が多い）で、時間に余裕があるとき  

#### データツリーに関する説明  
デルフト工科大学がいい説明資料を作っているので、[こちら](http://wiki.bk.tudelft.nl/toi-pedia/Basic_Data_Tree_Actions)を使いながら説明しようと思います。  

ほとんどの処理はFlattenとSimplifyが使えていれば、対応できるので、本授業では[データツリー説明](https://github.com/katsuya0719/design-engineering-class/blob/main/class2_grasshopper/%E3%83%87%E3%83%BC%E3%82%BF%E3%83%84%E3%83%AA%E3%83%BC%E8%AA%AC%E6%98%8E.gh)を使って、FlattenとSimplifyの使い方に関して細かく説明します。それ以外にもいろいろなデータツリーの構造があるので興味がある人は上の資料を活用ください。  

#### データの型に関する説明  
Grasshopperの全てのコンポーネントは操作する対象と動作（英語でいうSとVの関係みたいな）のどちらかと考えるとシンプル。  
動作は操作する対象に規定されるため、操作する対象のデータ型の特徴をつかんでしまえば、動作の部分は調べられるようになる（という持論）  

#### 動作は対象に規定されるというのはどういうことか？  
例えば、DecomposeBrepというコンポーネントのinputをみると、Brepのアイコンが表示される。これはDecomposeBrepという動作はBrepという対象に対してのみ使えるということ。  
pointでも、textでも、numberでもだめ。DecomposeBrepという動作はBrepという対象に対してのみ有効であるということ。  

#### データの型に関する説明  
データの型にあたるコンポーネントはParamsタブにまとまっています。(以下図参照)  

それでは、対象にあたるデータの型を列挙しながら、[データ型説明](https://github.com/katsuya0719/design-engineering-class/blob/main/class2_grasshopper/%E3%83%87%E3%83%BC%E3%82%BF%E5%9E%8B%E8%AA%AC%E6%98%8E.gh)を使って具体的に説明していきます。 

#### grasshopper上でPythonを使用する方法（時間が余ったら）  
4-7回目の授業では、構造に関する解析をPythonも使いながら行う予定です。ですので、pythonをGrasshopper上で使用する流れを[python説明](https://github.com/katsuya0719/design-engineering-class/blob/main/class2_grasshopper/python%E8%AA%AC%E6%98%8E.gh)でちょっと説明しておこうと思います。（Python自体に関する説明は3回目に行います）  

#### rhinoscriptsyntaxに関する説明  
pythonを用いてRhinocerosの機能を使う際にはrhinoscriptsyntaxというライブラリを使います。[rhinoscriptsyntaxのドキュメント](https://developer.rhino3d.com/api/RhinoScriptSyntax/#surface)について軽く授業で説明します。  


#### 次回に向けてgoogle colabの簡単な使い方説明  
次回の授業では、google colabを使って授業を進めます。


