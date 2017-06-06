## ハマリポイント
### インストールするまで
#### 共通
 - GUIインストール時に最低用意するもの
     - Raspberry Pi
     - microUSB電源 最低2.5A
     - miroSDカード class10/UHS-I対応 8～32GB、できれば2枚
         - インストールが終わった後、インストール直後のMicroSDを複製しておくため。
         - 2枚目はOS イメージの書き込み不要。
     - USBキーボード 
     - USBマウス
     - HDMIディスプレイ 横1366pixel 以上
     - HDMIケーブル
     - 有線LAN（ケーブル/HUB)+インターネット接続環境(ルータ)
 - MicroSDカードの相性
     - まずはMicroSDHC、class10/UHS-I対応、8G/16G/32G
     - 相性は http://elinux.org/RPi_SD_cards にまとまっている
     - Toshiba/Transcend/Samsungが相性よいと言われている(MicroSD＋ブランドで「はずれ」がない)
     - SunDisk/Team/PATRiOT/Kingstoneは相性悪いと言われている(ブランドだけ確認しても相性がわからない)
 - MicroSDカードのサイズ
     - 最低4Gということだが、GUIなしでも8G以上が必要
     - microSDの寿命上、できれば32GB (toshibaのもので1500円前後)
     - 64GB以上はつかえない(microSDXCはダメ)
 - MicroSDを作成するときに必要なもの
     - Windows/MacOSがインストールされたPC
     - NOOBSの場合: ZIPを解凍できるツール(7z/WinRARなど)
     - Raspbianをインストールする場合: Etcher https://etcher.io/ 
     - OSイメージ
         - https://www.raspberrypi.org/downloads/ からダウンロードしておく
         - https://www.raspberrypi.org/downloads/noobs/ から NOOBS LiteのDownload Zipをクリックして保存 (約32MB)
         - https://www.raspberrypi.org/downloads/raspbian/ から Raspbian Jessie with PIXELのDownload Zipをクリックして保存 (約1.3GB)
     - miroSDカード class10/UHS-I対応 8～32GB
     - PCにmicroSDスロットがない場合、USB接続のMicroSDカードリーダ

#### どのOSをインストールするのか
 - おすすめは「Raspbian Jessie with PIXEL」
 - NOOBS と Raspbianはどうちがうのか
     - NOOBS: New Out Of the Box Software 「全部ひとつの箱にはいってます」的。初心者向け。Raspbianも含んでいる。
         - メリット: Windows/MacOSでの作業はSDカードをフォーマットしてZIPの中にあるファイルをコピーするだけ。
         - デメリット: ダウンロードサイズ大きい。起動してからmicroSDカードを初期化するので、インストール時にRaspberry Piの作業が多い。
     - Raspbian: Debian for Raspberry Pi  「標準OS」
         - メリット: MicroSDカードができたらそのまま起動できる。ダウンロードのサイズ小さい。
         - デメリット: ダウンロードしたイメージファイルmicroSDに書き込むソフト(Etcher)が必要。
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
 - その他のOS
     - Ubuntu Mate https://ubuntu-mate.org/raspberry-pi/
         - もうひとつのディストリビューションであるUbuntuをベースにマルチメディアやRaspberryPi固有のパッケージを整備したもの
         - 商用アプリの利用時にUbuntuを要求するものがある
     - Windows IoT Core https://developer.microsoft.com/en-us/windows/iot/getstarted
         - MicrosoftがIoT用途に提供しているOSコア＋αのOS。通常のWindowsのアプリは動かない。
     - Google Coder for Raspberry Pi https://googlecreativelab.github.io/coder/
         - Web+IoTのプロトタイピングや教育用にGoogleが配布している環境
     - Android Things for Raspberry Pi 3 https://developer.android.com/things/hardware/raspberrypi.html
         - IoT用に最適化されたAndroid OS。Raspberry Pi 3でしか動かない。
     - Arch Linux https://wiki.archlinuxjp.org/index.php/Raspberry_Pi
         - Arch Linux は、あらゆる用途に対応できる万能 GNU/Linux ディストリビューションです。その開発は、シンプリシティ、ミニマリズム、およびコードの簡潔性に焦点を当てています。Arch は最小限の基本システムの状態でインストールされ、ユーザー自身が、ユーザーの理想とする環境のために必要なものだけをインストールして構築することができます。
     - DietPi http://dietpi.com/ 
         - 100MB以下で動作するDebian

#### NOOBSでのトラブル
 - NOOBSをダウンロードしたが、ZIPファイルの解凍ができない
     - ファイルが最後までダウンロードされているか確認
         - ファイルのSHA1がダウンロードページに書かれているものと合っているか確認する
　　　　         - Windowsの場合だと、certutil.exeコマンドで確認できる
       　　　　  - MacOSの場合だと opensslコマンドで確認できる
     - NOOBSには巨大なimageファイルが含まれており、OS標準のZipだと解凍できないことがあるよう。
     - 7z https://sevenzip.osdn.jp/ など大きなファイルに対応した解凍プログラムを使う
 - NOOBSのファイルがmicroSDにコピーできない
     - 他の用途に使っていたmicroSDだと、パーティションが切られていて修正できないことがある。
         - Etcherだとだいたい大丈夫だった
     - SD Card Formatter https://www.sdcard.org/downloads/formatter_4/ 
         - で一発でマッサラになる。
         
#### Raspbianでのトラブル
 - Etcherがエラーになる
     - ダウンロードしたイメージファイルが壊れていないか確認
              - ファイルのSHA1がダウンロードページに書かれているものと合っているか確認する
　　　　         - Windowsの場合だと、certutil.exeコマンドで確認できる
       　　　　  - MacOSの場合だと opensslコマンドで確認できる
     - Etcher https
     - Windows/MacOS/Linuxで利用可能
     - OSイメージをzipのまま利用可能
     - 

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
 
