Amazon Linux用Zabbix RPM
========================

ここで公開しているファイルは、Amazon Linux上でZabbixをRPMで導入するためのファイル群です。ZABBIX-JPで公開しているRPMをベースに作成しています。

前提条件
-------

ここで公開しているRPMは、ZABBIX-JPの公式なRPMではありません。

十分なテストができない部分もありますので、ご注意ください。

必要なRPM
---------

fpingやiksemel、iksemel-develのパッケージは、ZABBIX-JPで公開しているRHEL6用をご利用ください。

iksemel、iksemel-develのパッケージは、epelのパッケージでも稼動可能のようです。
fpingは、zabbix_server.confでSourceIPを指定して利用する場合は、ZABBIX-JP版が必須です。

ZABBIX-JPのRPMからの変更点
--------------------------

ここのディレクトリにあるバージョン1.8.8よりも前のSRPMでは、IPMIは無効にしてあります。
必要に応じてSPECファイルを修正して有効にする必要があります。
