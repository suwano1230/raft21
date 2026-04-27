# raft21（ソクタイプ型のDIYキーボード）
## レイアウト
[https://github.com/suwano1230/raft21/issues/1#issue-4335760611](https://private-user-images.githubusercontent.com/183176048/584201783-068149b4-a18e-4e09-b95e-374963c3ab1a.png?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NzcyOTM1NzcsIm5iZiI6MTc3NzI5MzI3NywicGF0aCI6Ii8xODMxNzYwNDgvNTg0MjAxNzgzLTA2ODE0OWI0LWExOGUtNGUwOS1iOTVlLTM3NDk2M2MzYWIxYS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjYwNDI3JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI2MDQyN1QxMjM0MzdaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0zMDQ2MWU1MmQxYmY3NmVmNWE3YmRmMmI0NDYyZmQ0NGNiMWFkMDllYjJhMjM4ZDdhYzMxY2JhZDg5ZTg2M2FlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZyZXNwb25zZS1jb250ZW50LXR5cGU9aW1hZ2UlMkZwbmcifQ.Z_Y41uW6XdzVDy2gI--_Z0zBU1Z1g6cYpk5nXLD99ag)
## 概要
Stenturaプロトコル互換で動くソクタイプ型のDIYキーボードです。  
ソクタイプは21キーで、キーの配置やキーキャップのサイズ、表面のくぼみ、高低差があるなどの特徴があります。  
Ploverでの動作は確認できましたが、Stenturaプロトコルと同一のものではありません。  
実機などから情報を得てStenturaプロトコルを再現したということはありません。  
また、キーキャップのサイズなどに関して、ソクタイプの厳密な再現とは言えない可能性があります。  
## PCB基盤
KiCadを使用して作成。MCUはRP2040（Raspberry Pi Pico）を使用します。  
MCUはピンヘッダを使わない直接はんだ付け、基盤の厚さは1.6mm厚の前提でケースを設計しています。
## スイッチプレート
KiCadを使用して作成。基盤を発注するのと同様に発注します。1.6mm厚の前提でケースは作成しています。
## キーキャップ
ソクタイプ型のキーキャップを再現するために3Dプリンターで作成します。
## ケース
3Dプリンターで作成します。`bottom-case.stl`
## 製作に必要なもの（上記以外）
| 名称　　　　  | 個数　　　　  | 備考   　　　　 
|:------------:|:------------:|:------------:|
| Raspberry Pi Pico  |      1      |     Pico 2 ではない   |
| PCBソケット  |     21     |スイッチを直接はんだ付けするなら不要|
| Cherry MX互換スイッチ  |     21     |     赤軸静音推奨　　　　     |
| プレートマウントスタビライザー 2U   |      4      |     MX用 |
| M2 6mm ねじ       |     7     |     底用ねじ     |
| M2 4mm ねじ       |     7     |     天用ねじ     |
| M2 8mm スペーサー  |     7     |    外径4.0mm以下   |
| Micro USB ケーブル  |     1     |   データ転送対応のもの |
| ゴム足 10mm  |     4     |     　高さ任意　　　     |

※PCBソケット（使用しないならスイッチ）と Raspberry Pi PicoをPCB基盤にはんだ付けする必要があります。

※両手の人差し指側につけるスタビライザーは、接触する箇所があります。  
　適宜ニッパー等でカットし、接触しないようにする必要があります。

※キースイッチとばねをルブ（潤滑）するなら、キースイッチ用とばね用の潤滑剤が必要です。

※キースイッチのばねを取り替えるなら、それも必要です。  
　赤軸静音使用時、20g 14mmは戻る力がぎりぎり足りませんでした。  
　19g 22mmはぎりぎりセーフでした。長期の使用に耐えるかは不明です。

## uf2ファイル
BOOTSELボタンを押しながらUSBケーブルを接続し、Raspberry Pi Picoを書き込みモードで立ち上げ、そのフォルダ内にuf2ファイルをコピーすることで書き込みできます。

## 参考
- [Plover](https://github.com/opensteno/plover)  
- [電子速記研究会 （はやとくんの会）](https://www.hayatokun.com/)
