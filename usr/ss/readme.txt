ss, sr -- PC から TaC7 へのファイル送信機能

ss と sr は、PC から TaC7 にファイルを送信するためのコマンドです．
ss を送信側（PC側）、sr を受信側（TaC7側）で実行します。
（ssコマンドを PC 側で起動すると TaC 側で srコマンドが自動的に起動されます．）
10KiB のファイルを約 15 秒程度で送信することができます。

書式
  ss <送信元ファイル名> [<受信側ファイル名>]
  <受信側ファイル名> を省略すると送信元と同じ名前のファイルに格納されます．
  （ファイル名は 8+3 形式でなければなりません．）

インストール
ss をインストールします．ss は macOS 用のプログラムです．
(macOS Catalina バージョン 10.15 で動作テストを行っています．)
0. C-- 開発環境インストール
  c-- version 3.2.1 以降が必要です．
  バージョンの確認は次のようにします．
  $ c-- -v
  必要に応じて新しいバージョンをインストールします．
1. make します
  $ make
2. インストールします
  $ sudo make install

使い方
1. TaC7 を PC に接続します
2. GNU Screen を起動します。
  $ screen /dev/tty.u[TAB]
  TacOSが正常に起動していることを確認します．
3. screen を [Ctrl+A][Ctrl+\] で終了します．
7. PC 側でファイ送信プログラムを起動します．
  $ ss sr.map
  .............................................................................
  ...........................................
  $
8. GNU Screen を起動し受信できていることを確認します．
　$ ls
　FileNameExt Attr Clst FileLength
  ...
  SR      MAP 0x20   18      7129
  ...
  $
