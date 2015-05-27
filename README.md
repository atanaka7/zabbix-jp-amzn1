Amazon Linux用Zabbix RPM
========================

ここで公開しているファイルは、Amazon Linux上でZabbixをRPMで導入するためのファイル群です。ZABBIX-JPで公開しているRPMをベースに作成しています。

前提条件
-------

ここで公開しているRPMは、ZABBIX-JPの公式なRPMではありません。

十分なテストができていない部分もありますので、ご注意ください。

必要なRPM
---------

fpingやiksemel、iksemel-develのパッケージは、Zabbix SIAで公開しているRHEL6用をご利用ください。

iksemel、iksemel-develのパッケージは、epelのパッケージでも稼動可能のようです。
fpingは、zabbix_server.confでSourceIPを指定して利用する場合は、Zabbix SIA版が必須です。

ZABBIX-JPのRPMからの変更点
--------------------------

ここのディレクトリにあるバージョン1.8.8よりも前のSRPMでは、IPMIは無効にしてあります。
必要に応じてSPECファイルを修正して有効にする必要があります。

RHEL 7対応について
--------------------

CentOS 7(RHEL 7互換)で動作確認を行っています。

Zabbix SIAのパッケージがRHEL 7対応になったので、それを参考にしたZabbix 2.4.5用から、systemdに対応するようになりました。

DBMSとしてMySQLの代わりにMariaDBを利用するようになっています。あと、Apache HTTP Serverの2.4系に対応するようconfigファイルを切り替えて利用するのが正式に組み込まれました。

CentOS 7.1.1503でzabbix_serverが起動できないのは、RHEL 7.1のバグです。対策としては、Fedora 20や21のtrousersの修正されたパッケージを参考にして、trousersのパッケージを更新すると起動できるようになります。

その他
------

古いマイナージョンのものは、脆弱性が確認されているものもありますので、より、新しいバージョンをご利用ください。

2.2.6-1、2.4.1-1は、Amazon Linux 2014.09公開後の物です。
2.4.5-1は、Amazon Linux 2015.03公開後の物です。

Amazon Linux 2014.09で、2.4.1-1を利用する際、Webインターフェースのセットアップウィザードが正常に機能しないことが確認されていますので、手動でファイル(/etc/zabbix/web/zabbix.conf.php)を作成して対応してください。(2014/10/10現在)

Amazon Linux 2015.03 と Zabbix 2.4.5の組み合わせであれば正常に稼働できています。(2015/05/27現在)

