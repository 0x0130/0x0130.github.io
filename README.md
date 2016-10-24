
javascript:(function(){/* style */var style = (function () {/*.toc{border: 1px solid #aaa;padding: 4px 12px;margin-bottom: 12px;position: relative;padding-top: 30px;}.toc-title{display: inline-block;width: auto;background-color: #ccc;position: absolute;left: 0px;top: 0px;font-size: 8pt;padding: 2px 4px;padding-right: 8px;color: #666;}.toc-h{font-size: 11pt;}.toc-h1{}.toc-h2{margin-left: 20px;}.toc-h3{margin-left: 40px;}*/}).toString().match(/[^]*\/\*([^]*)\*\/\}$/)[1];$('.toc-style').remove();$('body').append($('<style class="toc-style">\n' + style + '\n</style>'));/* toc frame */$('.toc').remove();var $toc = $('<div class="toc"><div class="toc-title">TOC</div></div>');$toc.prependTo($('.markdown-body'));/* each links */$('.markdown-body h1, .markdown-body h2, .markdown-body h3').each(function(){/* level */var tagName = $(this).prop('tagName').toLowerCase();/* link div */var $div = $('<div class="toc-h toc-' + tagName + '"></div>');/* link */var $a = $('<a href=""></a>');$a.appendTo($div);$a.text($(this).text());$a.attr('href', $(this).find('a:first').attr('href'));/* append */$toc.append($div);});})();




# 備忘録

## Apache2.2.x on systemctl (httpd.service)
* [Apache2.4 on CentOS7 でsystemctl start httpdで起動しない問題の対処法](http://qiita.com/DQNEO/items/7284687e22e3f9483984)
* [Apache2.2の設定ファイルをApache2.4に移植するためにやったことまとめ](http://qiita.com/DQNEO/items/1556a8e85af4bc40aad6)
* [Apache 2.4.4 - undefined symbol: ap_log_rerror](http://apache-http-server.18135.x6.nabble.com/Apache-2-4-4-undefined-symbol-ap-log-rerror-td5004721.html)

## 学習事項
* 統合認証基盤
* OpenLDAP
* [systemctlとUnitファイル](http://qiita.com/DQNEO/items/0b5d0bc5d3cf407cb7ff)
* [test](#sed)



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






