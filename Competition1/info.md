# Top
`random_state`は0で固定。

---
# sub1 (2021/11/06 AM 3:00)

## 概要
学習モデルは`sklearn.ensemble.RandomForestClassifier`

OneHotEncodingとSimpleImpute。Nameは相関がないと考えたのでdrop、Ticketはユニークな値が多いのでdrop。

## これから試すこと
Optunaでのハイパラチューニング  
別の学習モデル  
欠損値のある行をdrop  
OneHotをOrdinalEncodingに変える  
-> 他のカテゴリカルデータへのアプローチができる前処理を加えてみる  
データの相関を調べる   
CrossValidate  
アンサンブル学習  
Over-FittingとUnder-Fittingの検証  
`submission.csv`の作成方法を考える 

## スコア

0.761

---
# sub2 (2021/11/06 PM 3:00)

## 概要
学習モデルは`xgboost.XGBClassifier`

`numerical_cols`に対して`sklearn.preprocessing.StandardScaler`を用いた

前回の課題のうち、`submission.csv`の作成方法を変えてテストデータから`PassengerID`,`Perished`を切り取って`prediction`を代入。

他は同様。

## これから試すこと
Optunaでのハイパラチューニング  
別の学習モデル  
欠損値のある行をdrop  
OneHotをOrdinalEncodingに変える  
-> 他のカテゴリカルデータへのアプローチができる前処理を加えてみる  
データの相関を調べる   
CrossValidate  
アンサンブル学習  
Over-FittingとUnder-Fittingの検証  

データの偏りを調べる

## スコア

0.785




---
# sub3 (2021/11/07 AM 3:00)
`cross_val_score`を用いてのモデルの評価に変更。  
`optuna`でのハイパーパラメータチューニング  
データセットの分割に