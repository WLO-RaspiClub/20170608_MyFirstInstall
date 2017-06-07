## ハマリポイント
### インストールするまで
#### 共通
##### GUIインストール時に最低用意するもの
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
 
##### MicroSDカードの相性
 - まずはMicroSDHC、class10/UHS-I対応、8G/16G/32G
 - 相性は http://elinux.org/RPi_SD_cards にまとまっている
    - Toshiba/Transcend/Samsungが相性よいと言われている(MicroSD＋ブランドで「はずれ」がない)
    - SunDisk/Team/PATRiOT/Kingstoneは相性悪いと言われている(ブランドだけ確認しても相性がわからない)
##### MicroSDカードのサイズ
 - 最低4Gということだが、GUIなしでも8G以上が必要
 - microSDの寿命上、できれば32GB (toshibaのもので1500円前後)
 - 64GB以上はつかえない(microSDXCはダメ)
##### MicroSDを作成するときに必要なもの
 - Windows/MacOSがインストールされたPC
 - NOOBSの場合: ZIPを解凍できるツール(7z/WinRARなど)
 - Raspbianをインストールする場合: Etcher https://etcher.io/ が便利
     - Windows/MacOS/Linuxで利用可能
     - OSイメージをzipのまま利用可能
     - 簡単な手順:
       - Select Imageボタン押下⇒ダウンロードしたOSイメージを選択。zipのままでよい。
       - Select Driveボタン押下⇒インストール先のmicroSDを選択。選択間違うとPCを壊してしまうので注意。
         - Etcher立ち上げてからmicroSDを接続すると間違えにくい
       - Flashボタンで書き込み
         - PCの性能にもよるが5分～10分程度、書き込み後確認もしてくれる。
 - OSイメージ
     - https://www.raspberrypi.org/downloads/ からダウンロードしておく
     - https://www.raspberrypi.org/downloads/noobs/ から NOOBS LiteのDownload Zipをクリックして保存 (約32MB)
     - https://www.raspberrypi.org/downloads/raspbian/ から Raspbian Jessie with PIXELのDownload Zipをクリックして保存 (約1.3GB)
 - miroSDカード class10/UHS-I対応 8～32GB
 - PCにmicroSDスロットがない場合、USB接続のMicroSDカードリーダ

#### どのOSをインストールするのか
##### おすすめ
 - 「Raspbian Jessie with PIXEL」
##### NOOBS と Raspbianはどうちがうのか
 - NOOBS: New Out Of the Box Software 「全部ひとつの箱にはいってます」的。初心者向け。Raspbianも含んでいる。
     - メリット: Windows/MacOSでの作業はSDカードをフォーマットしてZIPの中にあるファイルをコピーするだけ。
     - デメリット: ダウンロードサイズ大きい。起動してからmicroSDカードを初期化するので、インストール時にRaspberry Piの作業が多い。
 - Raspbian: Debian for Raspberry Pi  「標準OS」
     - メリット: MicroSDカードができたらそのまま起動できる。ダウンロードのサイズ小さい。
     - デメリット: ダウンロードしたイメージファイルmicroSDに書き込むソフト(Etcher)が必要。
 - Windows/MacOSがある程度使えるならRaspbianがおすすめ
     - microSDの書き込みは、Etcher https://etcher.io/ を使うことで簡単になった
##### 「NOOBS」と「NOOBS Lite」の違い
 - 「NOOBS Lite」は最初のダウンロードサイズは小さい(32MBくらい)、起動してからRaspberryPiがOSイメージをダウンロードするので時間かかる
 - 「NOOBS」はRaspbianも含んでいるのでダウンロードサイズが大きい(1.3GB)
 - 高性能なPCが使えるなら「NOOBS」の方がトータル時間は短い、がそれならRaspbianがおすすめ
 - PCの空きディスク容量が少ないなら「NOOBS Lite」
##### 「Raspbian Jessie with PIXEL」と「Raspbian Jessie Lite」の違い
 - GUIで起動するのが「Raspbian Jessie with PIXEL」、CUI (文字だけのコンソール)で起動するのが「Raspbian Jessie Lite」
 - 初心者は「Raspbian Jessie with PIXEL」
 - 「ヘッドレス」運用（サーバとして使ったり、機器に組み込んで使う場合など）はGUIがない分性能が上がるので「Raspbian Jessie Lite」
 - 「Raspbian Jessie Lite」⇒「Raspbian Jessie with PIXEL」は可能。
##### その他のOS
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
##### NOOBSをダウンロードしたが、ZIPファイルの解凍ができない
 - ファイルが最後までダウンロードされているか確認
     - ファイルのSHA1がダウンロードページに書かれているものと合っているか確認する
        - Windowsの場合だと、certutil.exeコマンド(DOS窓)で確認できる
        - MacOSの場合だと opensslコマンドで確認できる
 - NOOBSには巨大なimageファイルが含まれており、OS標準のZipだと解凍できないことがあるよう。
     - 7z https://sevenzip.osdn.jp/ など大きなファイルに対応した解凍プログラムを使う
##### NOOBSのファイルがmicroSDにコピーできない
 - 他の用途に使っていたmicroSDだと、パーティションが切られていて修正できないことがある。
     - Etcherだとだいたい大丈夫だった
 - SD Card Formatter https://www.sdcard.org/downloads/formatter_4/ 
     - で一発でマッサラになる。
         
#### Raspbianでのトラブル
##### Etcherがエラーになる
     - ダウンロードしたイメージファイルが壊れていないか確認
         - ファイルのSHA1がダウンロードページに書かれているものと合っているか確認する
　　　　         - Windowsの場合だと、certutil.exeコマンド(DOS窓)で確認できる
       　　　　  - MacOSの場合だと opensslコマンドで確認できる

     - Windows/MacOS/Linuxで利用可能
     - OSイメージをzipのまま利用可能

#### インストール後
 - Raspbian起動時のエラー
     - HDMIモニタになにも表示されない
         - LEDを確認する
             - 赤LEDついてない: 電源供給されていない
             - 赤LED点滅: 電源電圧が低い/電流が少ない⇒ACアダプタ、ケーブル確認
             - 緑LED点滅: 起動シーケンスに問題あり 1点滅/SD形式違い 2点滅/SD不良 3点滅/start.elf不良 4点滅/start.elf起動不良 など
             - 緑消灯: 起動しているがHDMIに表示されない ケーブル不良、HDMI形式違い
     - 虹色四角が表示したまま
          - GPUは起動したがCPU起動していない。 /boot/config.txtを変更している場合は確認、していない場合はmicroSDカード不良
     - HDMIモニターが乱れる
          - /boot/config.txtで解像度変更している場合に解像度があってない。していない場合は対応していないHDMI解像度⇒/boot/config.txtを要修正。
 - 起動途中で再起動してしまう
     - 電源電圧が低かったり電流が少なかったりすると、起動途中でたりなくなって再起動してしまう
 - Panic表示
     - USB接続したハードウェアが正しく動かない
         - USB接続の周辺機器を抜いてみる
     - microSD不良
         - 正しくOSが書き込まれていない
 - 参考: http://elinux.org/R-Pi_Troubleshooting
 
### インストール後の初期設定
 - MicroSDのサイズについて
     - OSイメージは4GBを前提に導入される。8GB以上の場合はパーティションの拡張をしないと最大サイズまで使えない
     - 初回起動時に自動で実行される
         - 実行されなかった場合は、raspi-configで実施できる
 - パスワード変更
     - 標準ユーザ「pi」のパスワードはデフォルト「raspberry」なので、必ず変更しておく
     - GUI: 左上メニュー⇒Preferences⇒Raspberry Pi Configuration⇒Systemタブの「Change Password」ボタン
     - CUI: sudo raspi-config⇒ 1.Change User Password
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
##### Raspberry Pi Software Guide
  - https://www.raspberrypi.org/learning/software-guide/quickstart/
  - 公式なので鉄板
  - インストールビデオもある
  - 英語
##### ラズパイマガジンのインストール解説
  - 書籍、本屋で買える 2180円+税
  - 日本語
  - 隔月刊で最新情報に更新される
     
### Raspbian
##### からあげさんのBLOG http://karaage.hatenadiary.jp/ 
  - http://karaage.hatenadiary.jp/entry/2016/04/03/080000
  - 新しいRaspberry Piがでたら更新してもらえる

### その他おすすめ情報サイト
 - Freewing http://www.neko.ne.jp/~freewing/raspberry_pi/
 - QiitaのRaspberryPi記事 http://qiita.com/tags/Raspberry
 
