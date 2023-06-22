演習5 パーミッション
=================

# 権限が無い場合の挙動の確認
(1) 次のコマンドで、ex05フォルダに移動してください。

```shell
$ cd ~/command-exercises/ex05
```

(2) 次のコマンドで、ex05フォルダ配下にp1フォルダ、さらにその配下にsample.shがあることを確認してください。

```shell
$ ls -alh p1/
total 8
drwxr-xr-x@ 3 <ユーザー名>  staff    96B Jun 13 10:03 .
drwxr-xr-x@ 3 <ユーザー名>  staff    96B Jun 13 10:03 ..
-rwxr-xr-x@ 1 <ユーザー名>  staff    15B Jun 13 10:03 sample.sh
```

(3) 次のコマンドで、p1/sample.shのパーミッションを変更してください。

```shell
$ chmod 000 p1/sample.sh
```

(4) 次のコマンドで、p1/sample.shのパーミッションが`000`に変更されたことを確認してください。

```shell
$ ls -alh p1/
total 8
drwxr-xr-x@ 3 <ユーザー名>  staff    96B Jun 13 10:03 .
drwxr-xr-x@ 3 <ユーザー名>  staff    96B Jun 13 10:03 ..
----------  1 <ユーザー名>  staff    15B Jun 13 10:03 sample.sh
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

(7) 次のコマンドで、p1/sample.shに文字列を追記しようとすると、失敗することを確認してください。

```shell
$ echo "echo hello" >> p1/sample.sh
zsh: permission denied: p1/sample.sh
```

> これは、ユーザーがこのファイルの書き込み権限を持っていないことが原因です。

# 読み取り権限を付加する
(1) 次のコマンドで、ユーザーにp1/sample.shの読み取り権限を与えてください。

```shell
$ chmod 400 p1/sample.sh
```

> `chmod u=r p1/sample.sh`としても同様です。

(2) 次のコマンドで、ユーザーにp1/sample.shの読み取り権限のみが与えられていることを確認してください。

```shell
$ ls -al p1/
total 8
drwxr-xr-x@ 3 <ユーザー名>  staff  96 Jun 13 11:57 .
drwxr-xr-x@ 3 <ユーザー名>  staff  96 Jun 13 13:21 ..
-r--------@ 1 <ユーザー名>  staff  21 Jun 13 11:57 sample.sh
```

(3) 次のコマンドで、p1/sample.shを読み取ってください。

```shell
$ cat p1/sample.sh
echo こんにちは
```

(4) 次のコマンドで、p1/sample.shを実行しようとすると、失敗することを確認してください。

```shell
$ ./p1/sample.sh
zsh: permission denied: ./p1/sample.sh
```

(5) 次のコマンドで、p1/sample.shに文字列を追記しようとすると、失敗することを確認してください。

```shell
$ echo "echo hello" >> p1/sample.sh
zsh: permission denied: p1/sample.sh
```

# 書き込み権限を付加する
(1) 次のコマンドで、ユーザーにp1/sample.shの書き込み権限を与えてください。

```shell
$ chmod 200 p1/sample.sh
```

> `chmod u=w p1/sample.sh`としても同様です。

(2) 次のコマンドで、ユーザーにp1/sample.shの読み取り権限のみが与えられていることを確認してください。

```shell
$ ls -al p1/
total 8
drwxr-xr-x@ 3 <ユーザー名>  staff  96 Jun 13 11:57 .
drwxr-xr-x@ 3 <ユーザー名>  staff  96 Jun 13 13:21 ..
--w-------@ 1 <ユーザー名>  staff  21 Jun 13 11:57 sample.sh
```

(3) 次のコマンドで、p1/sample.shに文字列を追記してください。

```shell
$ echo "echo hello" >> p1/sample.sh
```

(4) 次のコマンドで、p1/sample.shを実行しようとすると、失敗することを確認してください。

```shell
$ ./p1/sample.sh
zsh: permission denied: ./p1/sample.sh
```

(5) 次のコマンドで、p1/sample.shを読み取ろうとすると、失敗することを確認してください。

```shell
$ cat p1/sample.sh
cat: p1/sample.sh: Permission denied
```

# 実行権限を付加する
(1) 次のコマンドで、ユーザーにp1/sample.shの実行権限を与えてください。

```shell
$ chmod 100 p1/sample.sh
```

> `chmod u=x p1/sample.sh`としても同様です。

(2) 次のコマンドで、ユーザーにp1/sample.shの実行権限のみが与えられていることを確認してください。

```shell
$ ls -al p1/
total 8
drwxr-xr-x@ 3 <ユーザー名>  staff  96 Jun 13 11:57 .
drwxr-xr-x@ 3 <ユーザー名>  staff  96 Jun 13 13:21 ..
---x------@ 1 <ユーザー名>  staff  21 Jun 13 11:57 sample.sh
```

(3) 次のコマンドで、p1/sample.shを読み取ろうとすると、失敗することを確認してください。

```shell
$ cat p1/sample.sh
cat: p1/sample.sh: Permission denied
```

(4) 次のコマンドで、p1/sample.shに文字列を追記しようとすると、失敗することを確認してください。

```shell
$ echo "echo hello" >> p1/sample.sh
zsh: permission denied: p1/sample.sh
```

(5) 次のコマンドで、p1/sample.shを実行しようとすると、失敗することを確認してください。これは、シェルスクリプトを実行するにはインタープリター（シェルスクリプトを解釈して実行するプログラム）が読み取る権限も必要だからです。

```shell
$ ./p1/sample.sh
cat: p1/sample.sh: Permission denied
```

(6) 次のコマンドで、ユーザーにp1/sample.shの実行権限を与えてください。

```shell
$ chmod 500 p1/sample.sh
```

> `chmod u=rx p1/sample.sh`としても同様です。

(7) 次のコマンドで、ユーザーにp1/sample.shの読み取り権限と実行権限のみが与えられていることを確認してください。

```shell
$ ls -al p1/
total 8
drwxr-xr-x@ 3 <ユーザー名>  staff  96 Jun 13 11:57 .
drwxr-xr-x@ 3 <ユーザー名>  staff  96 Jun 13 13:21 ..
-r-x------@ 1 <ユーザー名>  staff  21 Jun 13 11:57 sample.sh
```

(8) 次のコマンドで、p1/sample.shを実行してください。

```shell
$ ./p1/sample.sh
こんにちは
hello
```
