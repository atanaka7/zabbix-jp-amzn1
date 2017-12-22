Amazon Linux用Zabbix RPM
========================

ここで公開しているファイルは、Amazon Linux上でZabbixをRPMで導入するためのファイル群です。ZABBIX-JPで公開しているRPMをベースに作成しています。

前提条件
-------

ここで公開しているRPMは、ZABBIX-JPの公式なRPMではありません。

十分なテストができていない部分もありますので、ご注意ください。

必要なRPM
---------

fpingやiksemel、iksemel-develのパッケージは、Zabbix LLCで公開しているRHEL6用をご利用ください。
Amazon Linux 2の場合は、RHEL 7用を選択した方が良いでしょう。

iksemel、iksemel-develのパッケージは、epelのパッケージでも稼動可能のようです。
fpingは、zabbix_server.confでSourceIPを指定して利用する場合は、Zabbix LLC版か、バージョン3以降が必須です。

ZABBIX-JPのRPMからの変更点
--------------------------

ここのディレクトリにあるバージョン1.8.8よりも前のSRPMでは、IPMIは無効にしてあります。
必要に応じてSPECファイルを修正して有効にする必要があります。

RHEL 7対応について
--------------------

CentOS 7(RHEL 7互換)で動作確認を行っています。

Zabbix LLCのパッケージがRHEL 7対応になったので、それを参考にしたZabbix 2.4.5用から、systemdに対応するようになりました。

DBMSとしてMySQLの代わりにMariaDBを利用するようになっています。あと、Apache HTTP Serverの2.4系に対応するようconfigファイルを切り替えて利用するのが正式に組み込まれました。

CentOS 7.1.1503でzabbix_serverが起動できないのは、RHEL 7.1のバグです。対策としては、yum updateを実行するなどして、trousersのパッケージを修正されたパッケージに更新するようにしてください。

その他
------

古いマイナージョンのものは、脆弱性が確認されているものもありますので、より、新しいバージョンをご利用ください。

2.2.6-1、2.4.1-1は、Amazon Linux 2014.09公開後の物です。
2.4.5-1は、Amazon Linux 2015.03公開後の物です。

Amazon Linux 2014.09で、2.4.1-1を利用する際、Webインターフェースのセットアップウィザードが正常に機能しないことが確認されていますので、手動でファイル(/etc/zabbix/web/zabbix.conf.php)を作成して対応してください。(2014/10/10現在)

Amazon Linux 2015.03 と Zabbix 2.4.5の組み合わせであれば正常に稼働できています。(2015/05/27現在)

Zabbix 3.0.1は、Amazon Linux 2015.09上で確認しました。PHPが5.6になっているので、/etc/php.ini内のalways_populate_raw_post_dataの値を-1に設定してください。
Zabbix 3.0.1は、CentOS 6.7上でも確認しています。ただし、SMTP Authenticationが利用できないのと、PHP 5.4を利用できるようにするため、SCLを有効にしてphp54を利用する用にパッケージの依存関係を設定してありますのでご注意ください。(2016/02/29現在)

Zabbix 3.0.4では、CentOS 6用の設定追加を止めました。
必要となるPHPの環境に何を利用するかによってパッケージの依存関係も異なるので、Zabbix LLCが公開しているものと同様になっているはずです。(2016/08/01現在)

Zabbix 3.4.4-2で、Amazon Linux 2への対応を行ってみました。(2017/12/22現在)
fpingやiksemelなどは、RHEL 7用のSRPMからビルドすることをお勧めします。

