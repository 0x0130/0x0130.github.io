# 備忘録

## 正規表現(拡張正規表現)

|code|説明|備考|
|:--|:--|:--|
|`.`|任意の一文字||
|`*`|0回以上の繰り返し||
|`+`|1回以上の繰り返し||
|`[a-z]`|a~zの中の任意の一文字||
|`[A-Z]`|A~Zの中の任意の一文字||
|`[0-9]`|0~9の中の任意の一文字||
|`[a-zA-Z0-9]`|ぜんぶ||
|`[^a-z]`|a~z以外ぜんぶ||
|`^abc`|文字列の最初のa||
|`xyz$`|文字列の最後のz||



## /dev

`/dev/null` ... nullデバイス

`/dev/stdin` ... 標準入力

`/dev/stdout` ... 標準出力

`/dev/stderr` ... 標準エラー出力



## bash
`$?` = 返値
`$#` = 引数の数
`$*` = 引数のリスト(""でくくるとひとつの引数扱い ... "1 2 3 4")
`$@` = 引数のリスト(""でくくってもリスト扱い ... "1" "2" "3" "4")
`$$` = 現在のプロセスのPID



## sed

    echo -e 'abc\nabcabc\nabcabcabc' | sed 's/abc/ABC/'

['s/a/A/'] 1行につき最初の1回の出現のみ置換

    echo -e 'abc\nabcabc\nabcabcabc' | sed 's/abc/ABC/g'

['s/a/A/g'] 出てくる分だけ全部置換

    echo -e 'abc\nabcdef\nabcdefabc' | sed -e 's/abc/ABC/g' -e 's/def/DEF/g'

[-e] 複数条件

    echo -e 'abc\nabcdef\nabcdefabc' | sed -r 's/[a-z]+f/FFF/g'

[-r] 拡張正規表現

    echo -e 'abc\nabcdef\nabcdefabc' | sed -r 's/[a-z]+f/FFF/g'

[-r] 拡張正規表現

    echo -e 'abc\nabcdef\nabcdefabc' | sed -r '/def$/d'

['/パターン/d'] パターンにマッチする行を削除

    echo -e 'abc\nabcdef\nabcdefabc' | sed -r '/def$/!d'

['/パターン/!d'] パターンにマッチする行!!以外!!を削除。
grepとして使える！

#EOF




