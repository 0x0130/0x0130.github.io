# 備忘録

## Apache2.2.x on systemctl (httpd.service)
* [Apache2.4 on CentOS7 でsystemctl start httpdで起動しない問題の対処法](http://qiita.com/DQNEO/items/7284687e22e3f9483984)
* [Apache2.2の設定ファイルをApache2.4に移植するためにやったことまとめ](http://qiita.com/DQNEO/items/1556a8e85af4bc40aad6)
* [Apache 2.4.4 - undefined symbol: ap_log_rerror](http://apache-http-server.18135.x6.nabble.com/Apache-2-4-4-undefined-symbol-ap-log-rerror-td5004721.html)

## 学習事項
* 統合認証基盤
* OpenLDAP
* [systemctlとUnitファイル](http://qiita.com/DQNEO/items/0b5d0bc5d3cf407cb7ff)



## いいかんじのオプション
|code|説明|備考|
|:--|:--|:--|
|`grep --color=always`|`grep`のマッチング色付き表示がいいかんじなる||



## 環境変数
|code|説明|備考|
|:--|:--|:--|
|`HISTTIMEFORMAT='%Y-%m-%dT%T%z '`|`history`にコマンド実行時刻を記録する||



## bash
|code|説明|備考|
|:--|:--|:--|
|`$?`|返値||
|`$#`|引数の数||
|`$*`|引数のリスト|`""`でくくるとひとつの引数扱い(`"1 2 3 4"`)|
|`$@`|引数のリスト|`""`でくくってもリスト扱い(`"1" "2" "3" "4"`)|
|`$$`|現在のプロセスのPID||



## sed
|code|説明|備考|
|:--|:--|:--|
|`sed 's/abc/ABC/' $file`|`'s/a/A/'` 1回/1行の置換||
|`sed 's/abc/ABC/g' $file`|`'s/a/A/g'` ∞回/1行の置換||
|`sed -e 's/abc/ABC/g' -e 's/def/DEF/g' $file`|`-e`複数条件||
|`sed -r 's/[a-z]+f/FFF/g' $file`|`-r` 拡張正規表現||
|`sed -r 's/[a-z]+f/FFF/g' $file`|`-r` 拡張正規表現||
|`sed -r '/def$/d' $file`|`'/pattern/d'` マッチする行を削除||
|`sed -r '/def$/!d' $file`|`'/pattern/!d'` マッチする行以外を削除|`grep`として使える！|



## 正規表現(拡張正規表現)
|code|説明|備考|
|:--|:--|:--|
|`.`|任意の一文字||
|`*`|0回以上の繰り返し||
|`+`|1回以上の繰り返し||
|`[a-z]`|a~zの中の任意の一文字||
|`[A-Z]`|A~Zの中の任意の一文字||
|`[0-9]`|0~9の中の任意の一文字||
|`[a-zA-Z0-9]`|`[]`の中身ぜんぶ||
|`[^a-z]`|`[]`の中身以外ぜんぶ||
|`^abc`|文字列の最初のabc|`abcdefg...` ... OK `aabcdefg...` ... NG|
|`xyz$`|文字列の最後のxyz|`...vwxyz` ... OK `...vwxyzz` ... NG|



## /dev
|code|説明|備考|
|:--|:--|:--|
|`/dev/null`|nullデバイス||
|`/dev/stdin`|標準入力||
|`/dev/stdout`|標準出力||
|`/dev/stderr`|標準エラー出力||






