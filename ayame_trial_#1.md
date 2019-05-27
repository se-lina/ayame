# NAME

`ayame_trial_#1 - 試作機#1`

# SYNOPSIS

勉強会用ドローンキット試作機の設計仕様書

# QA

traial_#1 機の品質基準については下記の項目とする

- ドローンキットの組み立ておよび運転操作は、18歳以上の成人および成人同伴の場合を想定する
- 無風状態の室内での組み立ておよび運転操作を想定とする
- 保証対象はキット組み立て前の状態での部品不具合や欠品のみとし組み立て後は対象外とする
- キット組み立て後の操作においての怪我や物損などにおいては保証の対象外とする

# MATERIAL

組み立てキットについての部品一覧

__駆動部分__

- プロペラ: DJI Tello ミニドローン用プロペラ - 4個
- モーター: Rantow RCミニドローネ 8520 コアレスモーター - 4個

__フレーム__

- 飛行用フレーム: AYAME オリジナルフレームプレート - 1個

__フライトコントローラー__

- 制御コントローラー: Raspberry Pi Zero WH - 1個
- 制御コントローラーシステム入りSDカード: ラズビアン バージョン ** - 1枚
- モーター電力変換用回路基盤: AYAME オリジナル回路基盤 - 1個

__電源__

- モータ駆動用バッテリー: 3.7V***mA リチウムイオン電池
- Raspberry Pi 用アダプター: マイクロ USB アダプター電源 (出力 5V, 2.5A)
- 動作確認用電池ホールド(スイッチ付き): 単三乾電池用 - 1個
- 動作確認用電池: 単三乾電池 - 1個

__接続用ケーブル各種__

- 通電確認用ブレッドボード: ***製 - 1個
- ジャンパー線(オス-オス): ***ミリ - 4本

__組み立て操作マニュアル__

- 組み立てマニュアル: AYAMEオリジナル組み立てマニュアル
- 操作マニュアル: AYAMEオリジナル操作

# MANUAL

組み立て学習マニュアル

```
この試作機は開発中の試作機を流用しており、ayame ドローンキットの概要を
理解していただくためにご用意している
この試作機の基本設計をもとに一般販売むけのドローンキットが開発、製造される予定である
```

プロペラとモーターの動作確認

```
一般的にドローンの推進力は4つのプロペラの回転によって実現している
プロペラとモーターは時計回りのモーター2個と
半時時計回りのモーター2個の組み合わせで実現する
```

- 時計回りモーター(cw): 配線(白+黒線) - 2個
- 反時計回りモーター(ccw): 配線(青+黒線) - 2個
- プロペラ(cw):  (1もしくは3) * 2個
- プロペラ(ccw): (2もしくは4) * 2個

```
CWプロペラには、モーター取り付け部付近に印（凸部）
CWモーターにもケース部分に印（凸部）
CCWプロペラとCCWモーターには印はない
```

フレームに対してのモーターの取り付け箇所は下記を想定する

- 1: 左前(cw)
- 2: 右前(ccw)
- 3: 右後(cw)
- 4: 左後(ccw)

```
取り付け箇所については別途イラストを参考にするのがよい
ポイントは対角線上は同じ回転方向のモーターを配置する
```

通電するための事前知識

```
ブレシレスモーターとはDCモーターと呼ばれるモーターになる
DCモーターの配線はプラス、マイナスを逆につないでもモーターは回る
逆に電気を流すとモーターの回転も逆になることを覚えておく
今回は下記の色分けでプラス、マイナスのつなぎ方をしてみる
```

- 時計回りモーター(cw): 白->プラス、黒線->マイナス
- 反時計回りモーター(ccw): 青->プラス、黒線->マイナス

```
DCモーターは電気を流せば流すだけ早く回転する特徴がある
そのモーターの性能以上の電気を流すと最終的には壊れてしまう
適正な電気の量はモーターごとに異なるので、そのモーターの技術資料を調査しておく
今回のコアレスモーターは3.7vを適正と推測する、その理由は別途説明
```

電源を用意する

```
実際に空に飛ばす段階においてはモーター駆動用の電源はリチウムイオン電池を活用することがおおい
リチウムイオン電池は大抵の場合は充電可能になっており、電池の大きさに対しての
供給できる電気の量も多いことや一般的に入手がしやすことが理由になる
今回は仕組みを理解していただくことを目的としているので電源に乾電池を活用する
```

- 単三乾電池: アルカリ * 1個
- 単三乾電池用ホルダー: ブレッドボード接続端子付き * 1個