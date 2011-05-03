Amazon Linux用Zabbix RPM
========================

ここで公開しているファイルは、Amazon Linux上でZabbixをRPMで導入するためのファイル群です。ZABBIX-JPで公開しているRPMをベースに作成しています。

前提条件
-------

ここで公開しているRPMは、ZABBIX-JPの公式なRPMではありません。

十分なテストができない部分もありますので、ご注意ください。

必要なRPM
---------

fpingやiksemel、iksemel-develのパッケージは、ZABBIX-JPで公開しているRHEL5用をご利用ください。

2011/05/03現在、gnutlsのバージョンが上がってしまってZABBIX-JPで公開しているバージョンがインストールできない場合は、iksemel-1.4-1.amzn1.src.rpmを利用してRPMを作成して利用してみて下さい。

ZABBIX-JPのRPMからの変更点
--------------------------

Amazon Linux用のOpenIPMI-libsが用意できていないため、IPMIは無効にしてあります。
