## ハマリポイント
### インストールするまで
#### 共通
 - MicroSDカードの相性
     - まずはMicroSDHC、class10/UHS-I対応、8G/16G/32G
     - 相性は http://elinux.org/RPi_SD_cards にまとまっている
     - Toshiba/Transcend/Samsungが相性よいと言われている(MicroSD＋ブランドではずれがない)
     - SunDisk/Team/PATRiOT/Kingstoneは相性悪いと言われている(動くカードとそうでないものがある)
 - MicroSDカードのサイズ
     - 最低4Gということだが、GUIなしでも8G以上が必要
     - microSDの寿命上、できれば32GB
     - 64GB以上はつかえない
 - インストール時に最低用意するもの
     - Raspberry Pi
     - microUSB電源 最低2.5A
     - miroSDカード
     - USBキーボード
     - USBマウス
     - HDMIディスプレイ 横1366pixel 以上
     - HDMIケーブル
     - 有線LAN
     
#### どのOSをインストールするのか
 - NOOBS と Raspbianはどうちがうのか
 - 「NOOBS」と「NOOBS Lite」の違い
 - 「Raspbian Jessie with PIXEL」と「Raspbian Jessie Lite」の違い
 - その他のOS
 
#### NOOBSの場合 
 - NOOBSをダウンロードしたが、ZIPファイルの解凍ができない
 - NOOBSのファイルがmicroSDにコピーできない
 
#### Raspbianの場合
 - microSDの作成方法

#### インストール後
 - Raspbian起動時のエラー
  - HDMIモニタになにも表示されない
  - Panic表示
 
### インストール後の初期設定
 - MicroSDのサイズについて
 - 時刻設定
 - ネットワーク設定
  - 有線LAN
  - 無線LAN
 - パッケージ更新
 - パッケージ更新が遅い
 - ターミナル
  - キーボードの表示と入力値が異なる
 
## おすすめインストール手順
### NOOBS
 - Raspberry Pi Software Guide
     - https://www.raspberrypi.org/learning/software-guide/quickstart/
     - 公式なので鉄板
     - インストールビデオもある
     - 英語
 - ラズパイマガジンのインストール解説
     - 書籍、本屋で買える 2180円+税
     - 日本語
     - 隔月刊で最新情報に更新される
     
### Raspbian
 - からあげさんのBLOG http://karaage.hatenadiary.jp/ 
     - http://karaage.hatenadiary.jp/entry/2016/04/03/080000
     - 新しいRaspberry Piがでたら更新してもらえる

### その他おすすめ情報サイト
 - Freewing http://www.neko.ne.jp/~freewing/raspberry_pi/
 - QiitaのRaspberryPi記事 http://qiita.com/tags/Raspberry
 
