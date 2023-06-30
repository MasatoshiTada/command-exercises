演習2 ファイルの読み込み
====================

# catコマンドでの読み込み
(1) 次のコマンドで、ex02フォルダに移動してください。

```shell
$ cd ~/command-exercises/ex02
```

(2) 次のコマンドで、web-server.logを読み込んでください。

```shell
$ cat web-server.log
2023-06-12T17:10:48.708027 INFO Nginx001 started.
2023-06-12T17:10:48.734154 INFO Nginx002 started.
...
2023-06-12T17:10:48.903662 INFO Nginx100 started.
```

# lessコマンドでの読み込み
(1) 次のコマンドで、web-server.logを読み込んでください。上下キーでスクロールできます。

```shell
$ less web-server.log
2023-06-12T17:10:48.708027 INFO Nginx001 started.
2023-06-12T17:10:48.734154 INFO Nginx002 started.
...
:
```

(2) qキーで終了してください。

# headコマンドでの読み込み
(1) 次のコマンドで、web-server.logを読み込んでください。

```shell
$ head -n 3 web-server.log
2023-06-12T17:10:48.708027 INFO Nginx001 started.
2023-06-12T17:10:48.734154 INFO Nginx002 started.
2023-06-12T17:10:48.735779 INFO Nginx003 started.
```

# tailコマンドでの読み込み
(1) 次のコマンドで、web-server.logを読み込んでください。

```shell
$ tail -n 3 web-server.log
2023-06-12T17:10:48.901049 INFO Nginx098 started.
2023-06-12T17:10:48.902097 INFO Nginx099 started.
2023-06-12T17:10:48.903662 INFO Nginx100 started.
```

# grepコマンドでの抽出
(1) 次のコマンドで、web-server.logから`ERROR`が含まれる行のみを抽出してください。

```shell
$ cat web-server.log | grep ERROR
2023-06-12T17:10:48.810022 ERROR Nginx040 failed!!!
```

> - `grep ERROR web-server.log`でも同様です。
> - `何らかのコマンド | grep キーワード`で、キーワードが含まれる行のみを表示できます。

# ファイルの書き込み（追記）
(1) 次のコマンドで、write.txtの内容を確認してください。

```shell
$ cat write.txt
こんにちは
```

> catコマンドでは分かりづらいですが「こんにちは」の後に改行が入っています。

(2) 次のコマンドで、write.txtの末尾に「こんばんは」を追記してください。

```shell
$ echo こんばんは >> write.txt
```

> `echo`は本来、標準出力にメッセージを表示するだけのコマンドです。
> `>>`（後の手順では`>`）によって、標準出力の内容をテキストファイルに無理やり移動させています（これをリダイレクトと言います）。

(3) 次のコマンドで、write.txtの内容を確認してください。

```shell
$ cat write.txt
こんにちは
こんばんは
```

> catコマンドでは分かりづらいですが「こんばんは」の後に改行が入っています。

# ファイルの書き込み（上書き）
(1) 次のコマンドで、write.txtの内容を確認してください。

```shell
$ cat write.txt
こんにちは
こんばんは
```

(2) 次のコマンドで、write.txtの内容を「さようなら」で上書きしてください。

```shell
$ echo さようなら > write.txt
```

(3) 次のコマンドで、write.txtの内容を確認してください。

```shell
$ cat write.txt
さようなら
```

> catコマンドでは分かりづらいですが「さようなら」の後に改行は入って**いません**。
