[![Build Status](https://travis-ci.org/silver13/BoldClash-BWHOOP-B-03.svg?branch=master)](https://travis-ci.org/silver13/BoldClash-BWHOOP-B-03)

# NFE Silverware WTW Edition - NFE_Silverware modified to work on Makerfire Armor65 Lite.
Last update 24.01.20

WTW (Wednesday Tokyo Whoopers) の有志の皆様のご協力で、NFE_Silverware版のデフォルト値にレート、EXPOを味付けし直したものを公開致します。(2019年11月に一度Ver1.1まで公開していましたが、バグフィクス等もあり少し修正を加えたのもあるので、改めて構築し直しました。) PID周りは、少し触ってみたものの結局はNFE仕様標準値に戻しています。AlienWhoop Zer0等で設定された値からの変更はありません。また今回ベース機体としておりますMakerfire Armor65 Liteは、自社サイト内で初期ファームウェアの公開を行っておりません。確認したところNFE_Silverware版そのままであるという事から、今回はArmor65 Lite動作確認済でのファームウェア(HEXファイル)の公開を致します。思わずスティックジェスチャー(スティックコマンド)でPID値を変更してしまい、元の状態に戻せなくなった場合においても、初期値に修復可能です。また仕様がほぼ同じBETAFPV Beta65 Liteなどにも適用可能です。

今回、レート値、EXPO値をそれぞれ、アクロモード、レベルモード(アングルモード)の標準値よりも絞り気味に変更しました。これはBetaflight等で採用されている【Project Mockingbird】の操作イメージに近づける為です。ですが、今回の利用対象者を下記のように想定しています。

 * トイドローンから卒業した、FPV飛行が間もないユーザ。
 * 目視飛行はある程度でき、目線でのホバリング、八の字飛行などは墜落せずに行える。
 * ゆっくりの飛行状態であれば、FPVでフープをくぐれるが、少し操作を行うと狙ったように全然飛べなくなる。
 * すぐにぶつけて墜落させてしまう…。
 * Betaflight設定が難しく、自分自身で設定が出来ない。パソコンがあまり得意ではない…。
 * Betaflightで設定はしてみたが、狙ったフープを上手くくぐれない。自身が想定している飛行経路をトレースできない。

このような場合に、ひたすらフープをくぐる練習をする、スピード感に慣れることを想定した設定値としました。またこの機体の特徴として、軽く障害物にぶつけ、ふらついた状態になったとしても、操作不能で墜落せず、Betaflightよりも上手に水平復帰が行えます。その為、より操縦に集中できるものと思います。是非ご活用ください。



## クレジット (Credits)

テスト飛行に協力いただきました、WTW参加の皆様に感謝致します。
 * Julyさん、増谷さん、松元さん、ジセイさん、深海さん、山口さん、Moccaさん、陰山さん

その時の様子はこちら
https://youtu.be/FCqBhdlICu4


また、mixiドローン友の会:Silverwareトピックと、その住人の皆様に感謝致します。
 * bedroom-flyer(BDrF)さん、Hittoさん、多くの先人な皆様


## ファームウェアダウンロード (Firmware Download)

最新ファームウェアのダウンロードは【Release】タブへ移動してください。
https://github.com/ToshihiroMakuuchi/NFE_Silverware_WTW_Edition/releases


## パラメータについて (config.h)

* ベース設定:Alienwhoop_ZERO → BWOOP
* レート(ロール&ピッチ):860 → 1000
* レート(ヨー):500 → 610
* アクロEXPO(ロール): 0.80 → 0.25
* アクロEXPO(ピッチ): 0.80 → 0.25
* アクロEXPO(ヨー): 0.60 → 0.38
* アングルEXPO(ロール): 0.55 → 0.15
* アングルEXPO(ピッチ): 0.0 → 0.15
* アングルEXPO(ヨー): 0.55 → 0.28
* アングルリミット:65度 → 73度
* 送信プロトコル:RX_SBUS → RX_BAYANG_PROTOCOL_TELEMETRY_AUTOBIND
* エアモード出力:5% → 4%
* バッテリーボルト:4.20 → 4.35

> ---【 Silverware/src/config.h 】---  
> #define BWHOOP  
> #define MAX_RATE 1000.0  
> #define MAX_RATEYAW 610.0  
> #define ACRO_EXPO_ROLL 0.25  
> #define ACRO_EXPO_PITCH 0.25  
> #define ACRO_EXPO_YAW 0.38  
> #define ANGLE_EXPO_ROLL 0.15  
> #define ANGLE_EXPO_PITCH 0.15  
> #define ANGLE_EXPO_YAW 0.28  
> #define LEVEL_MAX_ANGLE 73.0f  
> #define RX_BAYANG_PROTOCOL_TELEMETRY_AUTOBIND  
> #define IDLE_THR 0.04f  
> #define ACTUAL_BATTERY_VOLTAGE 4.35  
> #define REPORTED_TELEMETRY_VOLTAGE 4.35  

