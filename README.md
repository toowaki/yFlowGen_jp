# yFlowGen_jp
C言語(C,C++)のソースファイルを入力することでフローチャート(gml ファイル形式)を自動生成します。

[実行例]
下記コマンドをwindowsのコマンドプロンプトで実行。

例ではソースファイルとしてsample.cを指定。
```
yFlowGen.exe -f sample.c
```

![yFlowGenで生成したフローチャート例](http://toowaki.web.fc2.com/picture/yflow_img_for_github.png "")

　 
# yFlowGenの使い方
Windowsのコマンドプロンプトにて、yFlowGen.exeを実行することで、result_yFlowGenフォルダ以下にフローチャートのファイルを出力し、log_yFlowGen.txtに実行ログを出力します。実行の際は、下記の引数を指定してください。　なお、GUIでの環境(yFlowGenGUI.xlsm)も用意しています。
```
yFlowGen.exe -f <filePath> -no_compact -no_comment -out1file -color -debug -out_group_comment
もしくは
yFlowGen.exe -d <dirPath> -no_compact -no_comment -out1file -color -debug -out_group_comment

-f <filePath> : C言語で書かれたソースファイルのパス (-dを記載の場合は省略可能)
-d <dirPath>  : C言語で書かれたソースファイルを含んだフィルダのパス (-fを記載の場合は省略可能)
-out1file     : 1ソースファイルにつき1gmlファイルを出力する (省略可能) 
-no_compact   : 処理ブロックのサイズをできるだけ小さくする設定をOFF (省略可能)
-no_comment   : フローチャートにコメントを表示しない (省略可能) 
-no_color     : ブロックに色を付けない (省略可能)
-no_dec       : 宣言のみのブロックは表示しない(省略可能)
-out_group_comment : コメントをグループの外側に配置する(省略可能)
-no_disp_struct : struct, unionのフローは出力しない(省略可能)
-no_reset     : スクリプト実行時に結果フォルダを削除しない(省略可能)
-true_false   : if/else if文の真偽をTrue,Falseで記載する(未設定時はYes,Noで記載)
```
