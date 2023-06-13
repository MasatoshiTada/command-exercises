演習5 パーミッション
=================

# 権限が無い場合の挙動の確認
(1) 次のコマンドで、ex05フォルダに移動してください。

```shell
$ cd ~/command-exercises/ex05
```

(2) 次のコマンドで、ex05フォルダ配下にp1フォルダ、さらにその配下にsample.shがあることを確認してください。

```shell
$ ls -alh p1
total 8
drwxr-xr-x@ 3 mac-mr9v2j001  staff    96B Jun 13 10:03 .
drwxr-xr-x@ 3 mac-mr9v2j001  staff    96B Jun 13 10:03 ..
-rwxr-xr-x@ 1 mac-mr9v2j001  staff    15B Jun 13 10:03 sample.sh
```

(3) 次のコマンドで、p1/sample.shのパーミッションを変更してください。

```shell
$ chmod 000 p1/sample.sh
```

(4) 次のコマンドで、p1/sample.shのパーミッションが`000`に変更されたことを確認してください。

```shell
$ ls -alh p1             
total 8
drwxr-xr-x@ 3 mac-mr9v2j001  staff    96B Jun 13 10:03 .
drwxr-xr-x@ 3 mac-mr9v2j001  staff    96B Jun 13 10:03 ..
----------  1 mac-mr9v2j001  staff    15B Jun 13 10:03 sample.sh
```

(5) 次のコマンドで、p1/sample.shを実行しようとすると、失敗することを確認してください。

```shell
$ ./p1/sample.sh
zsh: permission denied: ./p1/sample.sh
```

> これは、ユーザーがこのファイルの実行権限を持っていないことが原因です。

(6) 次のコマンドで、p1/sample.shを読み取ろうとすると、失敗することを確認してください。

```shell
$ cat p1/sample.sh
cat: p1/sample.sh: Permission denied
```

> これは、ユーザーがこのファイルの読み取り権限を持っていないことが原因です。

(7) 次のコマンドで、p1/sample.shをviで開いてください。その後、iキーを押下して編集モードにしようとすると、ターミナル下部に警告メッセージが表示されることを確認してください。確認できたら、ESCキー押下→`:q!`で保存せずにviを終了してください。

```shell
$ vi p1/sample.sh
```

> これは、ユーザーがこのファイルの書き込み権限を持っていないことが原因です。

# 権限を付加する
(1) 次のコマンドで、ユーザーにp1/sample.shの読み取り権限を与えてください。

```shell
$ chmod 400 p1/sample.sh
```

> `chmod u=r p1/sample.sh`としても同様です。

(2) 次のコマンドで、p1/sample.shを読み取ってください。

```shell
$ cat p1/sample.sh
echo こんにちは
```

(3) 次のコマンドで、p1/sample.shを実行しようとすると、失敗することを確認してください。

```shell
$ ./p1/sample.sh
zsh: permission denied: ./p1/sample.sh
```

(4) 次のコマンドで、p1/sample.shをviで開いてください。その後、iキーを押下して編集モードにしようとすると、ターミナル下部に警告メッセージが表示されることを確認してください。確認できたら、ESCキー押下→`:q!`で保存せずにviを終了してください。

```shell
$ vi p1/sample.sh
```

(5) 次のコマンドで、ユーザーにp1/sample.shの書き込み権限を与えてください。

```shell
$ chmod 200 p1/sample.sh
```
