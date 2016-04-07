#Automatine Documents

##TOC
	
1. Introduction & Motivations
1. 導入
1. 構造
1. APIs
1. 逆引きAutomatine


##Introduction & Motivations

###intro
Automatineは、タイムライン上に状態やスクリプトを配置し実行できるユーティリティ。特に次のようなことを簡単に管理するのを目指している。

* タイムラインでキャラクターやゲーム自体の挙動を制御したい
* 条件分岐を入れてAIのようなものを作りたい
* 状態を持たせたい、別のタイムラインに引き継ぎたい(Condition)
* サーバなど、Unity外でも動かしたい(Portability)
* RuntimeとDataを分離したい(Updateable)
* コードからPlay中の実行、更新、追加を行う()
* GUIで設定の生成、変更、データ化を行う(Artist Friendly)


###Sequencerとの違い
Unity5.4以降でSeqencer(Timeline tool)が入るが、それとは異なる用途を目指している。


| やりたいこと        | Sequencer           | Automatine  |
| ------------- |-------------:| -----:|
| Assetをタイムラインにセット		| o | x |
|シーン単位で実行| o | o |
|キャラ単位でタイムライン実行| difficult | o |
|一部の動作を繰り返して実行| x | o |
|状態の保持、管理| not suite | o |
|状態遷移の定義、実行| x | o |
|スクリプトの実行| o | o |
|スクリプトの継続実行| ? | o |
|AIの実装| not aimed | o |


Sequencerがシネマティックなシーケンスを生成するのを主なMotivationにしているのに対し、Automatineはより細かい粒度での「キャラクターやオブジェクトの状態を管理し、スクリプトの実行と継続動作」を実現することを主な目的としている。


###特徴
すでに実装されている大きな特徴として次のようなものがある。

* MonoBehaviour、Assetへの依存を持たない、ピュアC#コード
* 実行のためのシングルトンインスタンスなどを一切持たないので導入や廃棄が楽
* 実行時、ゲームごとに独自定義した型とインスタンスを組み込むことができる
* フレーム単位での状態定義、取得が可能
* 通常のC＃スクリプトをセットして実行したり、Coroutineの継続的な実行が可能
* 実時間ではなく、カウント=実行回数ベースで動作する。個別に、1フレーム中で何回も実行することが可能
* GUIから、コードを吐き出す or データを吐き出すことが可能
* データ形式はJSON他が使用可能
* RuntimeがUnityに依存していないので他のプラットフォームでも動作する
* C#以外の言語でも同様のRuntimeを生成することが比較的容易(Go,Rust,Lua等)


##導入

☆Automatineを使い始めるにあたってのTutorial。

###インストール
Automatine フォルダをAssetsフォルダ以下に置く。
Assets/Automatine

###Automatine編集ウィンドウを開く
☆

###新しいAutoを作成、保存
☆GUIから。作成して名前をつけて、TimelineとTack置いて保存

###コードから使う
1. using Automatine;
1. ☆とか

###動かす
1. Update

###状態を取得する

###終了を検知する

###切り替えてみる
1. ☆new 

###停める
Updateをやめるか、frameを加算するのを停めると、停止する。

###特定のタイミングでRoutineコードを実行する
☆GUIからスクリプトをアタッチ、


##構造

☆簡単なレイヤーの紹介。  
Auto(s) / Timeline(s) / Tack(s) / Coroutine(s) | ConditionKey & Value

☆図

##APIs

☆AutoのAPI一覧、API Docの形式どうしようかな〜。


##逆引きAutomatine

☆こんなことがしたい、からFeaturesを紹介する。箇条書き


