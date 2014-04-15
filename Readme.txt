<mt:Version>からバージョンの枝番号を削除する

通常、テンプレートに書かれた<mt:Version> は6.0.3などのようにバージョン番号をすべて書き出します。

例）Mobanle Type <mt:Version>　=>Movable Type 6.0.3

このようにバージョンをすべて表示させたくないときの方法です。

MTのグローバル・モディファイアにMTタグの値を置き換えられる「regex_replace」と「replace」があります。
「regex_replace」と「replace」の違いは置き換える文字の指定に正規表現が使えるか、直接、置き換えるたい文字を指定するかです。

下記のように正規表現で書くことで、すべて書き出されていたバージョンが、メジャーバージョンのみの表示になります。

<$MTVersion regex_replace="/\..*/",""$>

例）Mobanle Type <$MTVersion regex_replace="/\..*/",""$>　=>Movable Type 6