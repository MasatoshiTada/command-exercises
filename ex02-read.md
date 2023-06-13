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
$ grep ERROR web-server.log
2023-06-12T17:10:48.810022 ERROR Nginx040 failed!!!
```
