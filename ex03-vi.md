演習3 viエディタ
==============

# viエディタでのテキストファイル編集
(1) 次のコマンドで、ex03フォルダに移動してください。

```shell
$ cd ~/command-exercises/ex03
```

(2) 次のコマンドで、ファイルの中にvi-sample.txtが存在することを確認してください。

```shell
$ ls -alh
total 0
drwxr-xr-x@  3 <ユーザー名>  staff    96B Jun 13 08:43 .
drwxr-xr-x  13 <ユーザー名>  staff   416B Jun 13 08:43 ..
-rw-r--r--@  1 <ユーザー名>  staff     0B Jun 13 08:43 vi-sample.txt
```

(3) 次のコマンドで、vi-sample.txtの中身が空であることを確認してください。

```shell
$ cat vi-sample.txt

```

(4) 次のコマンドで、vi-sample.txtを開いてください。

```shell
$ vi vi-sample.txt
```

(5) iキーを押下して、viを編集モードにしてください。

(6) 次のようにvi-sample.txtを編集してください。

```text
こんにちは
さようなら
```

(7) ESCキーを謳歌して、viをコマンドモードにしてください。

(8) `:q!`と入力後、Enterキーを押下してください。

> このコマンドは、編集内容を保存せずにviを強制終了します。

(9) 次のコマンドで、vi-sample.txtの中身が空のままであることを確認してください。

```shell
$ cat vi-sample.txt

```

(10) 次のコマンドで、vi-sample.txtを開いてください。

```shell
$ vi vi-sample.txt
```

(11) iキーを押下して、viを編集モードにしてください。

(12) 次のようにvi-sample.txtを編集してください。

```text
こんにちは
さようなら
```

(13) ESCキーを謳歌して、viをコマンドモードにしてください。

(14) `:wq`と入力後、Enterキーを押下してください。

> このコマンドは、編集内容を保存した後にviを終了します。

(15) 次のコマンドで、vi-sample.txtに中身が追加されたことを確認してください。

```shell
$ cat vi-sample.txt
こんにちは
さようなら
```

# 環境変数の設定

> ~/.zshrcファイルの編集は、vi以外のエディタ（VSCodeなど）でも可能です。
> 今回の演習では、練習のためにviを利用します。

(1) 次のコマンドで、~/.zshrcファイルを開いてください。

```shell
vi ~/.zshrc
```

(2) iキーを押下して、viを編集モードにしてください。

(3) ~/.zshrcファイルの先頭に以下の記述を追加してください。

```shell
export SAMPLE_GREET=こんにちは
```

(4) ESCキーを謳歌して、viをコマンドモードにしてください。

(5) `:wq`と入力後、Enterキーを押下してください。

(6) 次のコマンドで、~/.zshrcファイルの先頭に環境変数が記述されていることを確認してください。

```shell
$ head -n 3 ~/.zshrc
export SAMPLE_GREET=こんにちは
...
...
```

(7) 次のコマンドで、環境編集`SAMPLE_GREET`の値がまだ空であることを確認してください。

```shell
$ echo $SAMPLE_GREET

```

(8) 次のコマンドで、~/.zshrcの再読み込みを行ってください。

```shell
$ source ~/.zshrc

```

> このコマンドの代わりに、ターミナルの再起動をしても同様の効果が得られます。

(9) 次のコマンドで、環境編集`SAMPLE_GREET`に値が設定されていることを確認してください。

```shell
$ echo $SAMPLE_GREET
こんにちは
```

# 後片付け
(1) 次のコマンドで、~/.zshrcファイルを開いてください。

```shell
vi ~/.zshrc
```

(2) iキーを押下して、viを編集モードにしてください。

(3) `export SAMPLE_GREET=こんにちは`の行を削除してください。

(4) ESCキーを謳歌して、viをコマンドモードにしてください。

(5) `:wq`と入力後、Enterキーを押下してください。
