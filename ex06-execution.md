演習6 プログラムの実行
==================

# 実行ファイルにコンパイル
(1) 次のコマンドで、ex06フォルダに移動してください。

```shell
$ cd ~/command-exercises/ex06
```

(2) 次のコマンドで、C言語のソースコードmycmd.cを実行ファイルmycmdにコンパイルしてください。

```shell
$ gcc -o mycmd mycmd.c
```

(3) 次のコマンドで、ex06フォルダに実行ファイルmycmdが作成されたことを確認してください。

```shell
$ ls -alh
total 88
drwxr-xr-x@  5 <ユーザー名>  staff   160B Jun 30 15:22 .
drwxr-xr-x  19 <ユーザー名>  staff   608B Jun 30 15:22 ..
-rw-r--r--@  1 <ユーザー名>  staff   329B Jun 30 08:03 README.md
-rwxr-xr-x@  1 <ユーザー名>  staff    32K Jun 30 15:22 mycmd
-rw-r--r--@  1 <ユーザー名>  staff    95B Jun 30 08:08 mycmd.c
```

# 実行ファイルの実行確認①
(1) 次のコマンドで、command-exercisesフォルダに移動してください。

```shell
$ cd ~/command-exercises
```

(2) 次のコマンドで、ex06フォルダ内にmycmdがあることを確認してください。

```shell
$ ls -alh ex06
total 88
drwxr-xr-x@  5 <ユーザー名>  staff   160B Jun 30 08:03 .
drwxr-xr-x  19 <ユーザー名>  staff   608B Jun 30 08:06 ..
-rw-r--r--@  1 <ユーザー名>  staff   329B Jun 30 08:03 README.md
-rwxr-xr-x@  1 <ユーザー名>  staff    32K Jun 30 07:59 mycmd
-rw-r--r--@  1 <ユーザー名>  staff    83B Jun 30 07:57 mycmd.c
```

(3) 次のコマンドで、ex06/mycmdを実行してください。

```shell
$ ex06/mycmd
mycmdが正常に実行できました
```

> フォルダ名まで指定すれば（相対パスでも絶対パスでもOK）、実行ファイルmycmdがどこにあるか特定できるので、実行できます。

(4) 次のコマンドでmycmdを実行しようとすると、`command not found`と表示されることを確認してください。

```shell
$ mycmd
zsh: command not found: mycmd
```

> フォルダ名を指定していないため、実行ファイルmycmdがどこにあるか特定できないからです。

(5) 次のコマンドで、ex06フォルダに移動してください。

```shell
$ cd ex06
```

(6) 次のコマンドで、mycmdを実行してください。

```shell
$ ./mycmd
mycmdが正常に実行できました
```

(7) 次のコマンドでmycmdを実行しようとすると、`command not found`と表示されることを確認してください。

```shell
$ mycmd
zsh: command not found: mycmd
```

> 実は、実行可能ファイルの場所を探すための環境変数PATHには、カレントフォルダが含まれていません。なので、実行する際は`./mycmd`のように明示的に「カレントフォルダにあるmycmd」と指定する必要があります。

# 環境変数PATHの設定
(1) 次のコマンドで、~/.zshrcをviエディタで開いてください。

```shell
$ vi ~/.zshrc
```

(2) iキーを押下して、viを編集モードにしてください。

(3) ~/.zshrcファイルの先頭に以下の記述を追加してください。

```shell
export PATH=~/command-exercises/ex06:$PATH
```

> 最後の`:$PATH`を書かなかった場合、元々のPATHの値が失われます。その結果、`ls`などのコマンドが使えなくなります。

(4) ESCキーを謳歌して、viをコマンドモードにしてください。

(5) `:wq`と入力後、Enterキーを押下してください。

(6) 次のコマンドで、~/.zshrcファイルの先頭に環境変数が記述されていることを確認してください。

```shell
$ head -n 3 ~/.zshrc
export PATH=~/command-exercises/ex06:$PATH
...
...
```

(7) 次のコマンドで、環境変数`PATH`の値に`~/command-exercises/ex06`がまだ含まれていないことを確認してください。

```shell
$ echo $PATH
/usr/bin:/bin:/usr/sbin:/sbin:...
```

(8) 次のコマンドで、~/.zshrcの再読み込みを行ってください。

```shell
$ source ~/.zshrc

```

> このコマンドの代わりに、ターミナルの再起動をしても同様の効果が得られます。

(9) 次のコマンドで、環境変数`PATH`の値に`~/command-exercises/ex06`が含まれていることを確認してください。

```shell
$ echo $PATH
/Users/ユーザー名/command-exercises/ex06:/usr/bin:/bin:/usr/sbin:/sbin:...
```

# 実行ファイルの実行確認②
(1) 次のコマンドで、ユーザーホームフォルダに移動してください。

```shell
$ cd ~
```

(2) 次のコマンドで、mycmdを実行してください。

```shell
$ mycmd
mycmdが正常に実行できました
```

(3) 次のコマンドで、command-exercises/ex01フォルダに移動してください。

```shell
$ cd ~/command-exercises/ex01
```

(4) 次のコマンドで、mycmdを実行してください。

```shell
$ mycmd
mycmdが正常に実行できました
```

(5) 次のコマンドで、command-exercises/ex06フォルダに移動してください。

```shell
$ cd ~/command-exercises/ex06
```

(6) 次のコマンドで、mycmdを実行してください。

```shell
$ mycmd
mycmdが正常に実行できました
```

(7) 次のコマンドで、mycmdを実行してください。

```shell
$ ./mycmd
mycmdが正常に実行できました
```

> 実行ファイル名のみを指定した場合、環境変数PATHに指定したフォルダの中から順に検索します。

# 後片付け
(1) 次のコマンドで、~/.zshrcファイルを開いてください。

```shell
vi ~/.zshrc
```

(2) iキーを押下して、viを編集モードにしてください。

(3) `export PATH=~/command-exercises/ex06:$PATH`の行を削除してください。

(4) ESCキーを謳歌して、viをコマンドモードにしてください。

(5) `:wq`と入力後、Enterキーを押下してください。

(6) 次のコマンドで、~/.zshrcの再読み込みを行ってください。

```shell
$ source ~/.zshrc

```
