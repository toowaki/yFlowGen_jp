# yFlowGen_jp
yFlowGen.exeにC言語(C,C++)のソースファイルを入力することでフローチャートを自動生成します。
ファイル形式は、「GMLファイル」、「DOTファイル+SVGファイル」を選択可能です。
-	GMLファイルの場合、yEd Graph Editorのインストールが必要です。[https://www.yworks.com/products/yed/download#download]
-	DOTファイルの場合、Graphvizのインストールが必要です。[https://graphviz.org/download/]
 
[実行例] GMLファイル生成の場合
下記コマンドをwindowsのコマンドプロンプトで実行。
例ではソースファイルとしてsample.cを指定。
```
yFlowGen.exe -f sample.c
```
![yFlowGenで生成したフローチャート例](http://toowaki.web.fc2.com/picture/yFLowGne_pic_code2gml.png "")

[実行例] DOT + SVGファイル生成の場合
```
yFlowGen.exe -f sample.c -format dot
```
![yFlowGenで生成したフローチャート例](http://toowaki.web.fc2.com/picture/yFLowGne_pic_code2dot.png "")
　 
# yFlowGenの使い方
Windowsのコマンドプロンプトにて、yFlowGen.exeを実行することで、result_yFlowGenフォルダ以下にフローチャートのファイルを出力し、log_yFlowGen.txtに実行ログを出力します。実行の際は、下記の引数を指定してください。GUIでの環境(yFlowGenGUI.xlsm)については、yFlowGenGUI.xlsmに記載した「使い方」シートを御覧ください。
```
yFlowGen.exe -f <filePath> -no_compact -no_comment -out1file -color -debug -out_group_comment
もしくは
yFlowGen.exe -d <dirPath> -no_compact -no_comment -out1file -color -debug -out_group_comment

-f <filePath> : C言語で書かれたソースファイルのパス (-dを記載の場合は省略可能)
-d <dirPath>  : C言語で書かれたソースファイルを含んだフィルダのパス (-fを記載の場合は省略可能)
-format <format> : 「-format dot」と入力するとDOTとSVGファイルを生成します。(省略時はGMLを生成)
-out1file     : 1ソースファイルにつき1GMLファイルを出力する (省略可能) 
-no_compact   : 処理ブロックのサイズをできるだけ小さくする設定をOFF (省略可能)
-no_comment   : フローチャートにコメントを表示しない (省略可能) 
-no_color     : ブロックに色を付けない (省略可能)
-no_dec       : 宣言のみのブロックは表示しない(省略可能)
-out_group_comment : コメントをグループの外側に配置する(省略可能)
-no_disp_struct : struct, unionのフローは出力しない(省略可能)
-no_reset     : スクリプト実行時に結果フォルダを削除しない(省略可能)
-true_false   : if/else if文の真偽をTrue,Falseで記載する(未設定時はYes,Noで記載)
-no_connection_point : 接続点を追加しない(未設定時は接続点を追加)
```
