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

ZABBIX-JPのRPMからの変更点
--------------------------

Amazon Linux用のOpenIPMI-libsが用意できていないため、IPMIは無効にしてあります。
