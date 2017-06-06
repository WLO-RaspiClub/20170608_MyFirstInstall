## ハマリポイント
### インストールするまで
#### 共通
 - MicroSDカードの相性
     - まずはMicroSDHC、class10/UHS-I対応、8G/16G/32G
     - 相性は http://elinux.org/RPi_SD_cards にまとまっている
     - Toshiba/Transcend/Samsungが相性よいと言われている(MicroSD＋ブランドで「はずれ」がない)
     - SunDisk/Team/PATRiOT/Kingstoneは相性悪いと言われている(ブランドだけ確認しても相性がわからない)
 - MicroSDカードのサイズ
     - 最低4Gということだが、GUIなしでも8G以上が必要
     - microSDの寿命上、できれば32GB (toshibaのもので1500円前後)
     - 64GB以上はつかえない(microSDXCはダメ)
 - GUIインストール時に最低用意するもの
     - Raspberry Pi
     - microUSB電源 最低2.5A
     - miroSDカード class10/UHS-I対応 8～32GB、できれば2枚
     - USBキーボード 
     - USBマウス
     - HDMIディスプレイ 横1366pixel 以上
     - HDMIケーブル
     - 有線LAN（ケーブル/HUB)+インターネット接続環境(ルータ)
     
#### どのOSをインストールするのか
 - NOOBS と Raspbianはどうちがうのか
     - NOOBS: New Out Of the Box Software 「全部ひとつの箱にはいってます」的。初心者向け。Raspbianも含んでいる。
         - メリット: Windows/MacOSでの作業はSDカードをフォーマットしてZIPの中にあるファイルをコピーするだけ。
         - デメリット: ダウンロードサイズ大きい。起動してからmicroSDカードを初期化するので、インストール時にRaspberry Piの作業が多い。
     - Raspbian: Debian for Raspberry Pi  「標準OS」
         - メリット: MicroSDカードができたらそのまま起動できる。ダウンロードのサイズ小さい。
         - デメリット: ダウンロードしたイメージファイルmicroSDに書き込むソフトが必要。
     - Windows/MacOSがある程度使えるならRaspbianがおすすめ
         - microSDの書き込みは、Etcher https://etcher.io/ を使うことで簡単になった
 - 「NOOBS」と「NOOBS Lite」の違い
     - 「NOOBS Lite」は最初のダウンロードサイズは小さい(32MBくらい)、起動してからRaspberryPiがOSイメージをダウンロードするので時間かかる
     - 「NOOBS」はRaspbianも含んでいるのでダウンロードサイズが大きい(1.3GB)
     - 高性能なPCが使えるなら「NOOBS」の方がトータル時間は短い、がそれならRaspbianがおすすめ
     - PCの空きディスク容量が少ないなら「NOOBS Lite」
 - 「Raspbian Jessie with PIXEL」と「Raspbian Jessie Lite」の違い
     - GUIで起動するのが「Raspbian Jessie with PIXEL」、CUI (文字だけのコンソール)で起動するのが「Raspbian Jessie Lite」
     - 初心者は「Raspbian Jessie with PIXEL」
     - 「ヘッドレス」運用（サーバとして使ったり、機器に組み込んで使う場合など）はGUIがない分性能が上がるので「Raspbian Jessie Lite」
     - 「Raspbian Jessie Lite」⇒「Raspbian Jessie with PIXEL」は可能。

``` 
$ sudo apt-get update
$ sudo apt-get dist-upgrade
$ sudo apt-get install -y rpi-chromium-mods
$ sudo apt-get install -y python-sense-emu python3-sense-emu
$ sudo apt-get install -y python-sense-emu-doc realvnc-vnc-viewer
```

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
 
