演習04 ファイルの作成など
====================

# ファイルのコピー・リネーム・削除
(1) 次のコマンドで、ex04フォルダに移動してください。

```shell
$ cd ~/command-exercises/ex04
```

(2) 次のコマンドで、ex04フォルダ直下にcp-sample1.txtがあることを確認してください。

```shell
$ ls -alh
total 8
drwxr-xr-x@  3 <ユーザー名>  staff    96B Jun 13 09:29 .
drwxr-xr-x  16 <ユーザー名>  staff   512B Jun 13 09:29 ..
-rw-r--r--@  1 <ユーザー名>  staff    15B Jun 13 09:29 cp-sample1.txt
```

(3) 次のコマンドで、cp-sample1.txtの中身を確認してください。

```shell
$ cat cp-sample1.txt
こんにちは
```

(4) 次のコマンドで、cp-sample1.txtのコピーcp-sample2.txtを作成してください。

```shell
$ cp cp-sample1.txt cp-sample2.txt
```

(5) 次のコマンドで、ex04フォルダ直下にcp-sample2.txtが作成されたことを確認してください。

```shell
$ ls -alh
total 16
drwxr-xr-x@  4 <ユーザー名>  staff   128B Jun 13 09:31 .
drwxr-xr-x  16 <ユーザー名>  staff   512B Jun 13 09:32 ..
-rw-r--r--@  1 <ユーザー名>  staff    15B Jun 13 09:29 cp-sample1.txt
-rw-r--r--@  1 <ユーザー名>  staff    15B Jun 13 09:31 cp-sample2.txt
```

(6) 次のコマンドで、cp-sample2.txtの中身がcp-sample1.txtと同じであることを確認してください。

```shell
$ cat cp-sample2.txt
こんにちは
```

(7) 次のコマンドで、cp-sample2.txtのファイル名をcp-sample999.txtに変更してください。

```shell
$ mv cp-sample2.txt cp-sample999.txt
```

(8) 次のコマンドで、ファイル名が変更されたことを確認してください。

```shell
$ ls -alh                           
total 16
drwxr-xr-x@  4 <ユーザー名>  staff   128B Jun 13 09:34 .
drwxr-xr-x  16 <ユーザー名>  staff   512B Jun 13 09:34 ..
-rw-r--r--@  1 <ユーザー名>  staff    15B Jun 13 09:29 cp-sample1.txt
-rw-r--r--@  1 <ユーザー名>  staff    15B Jun 13 09:31 cp-sample999.txt
```

(9) 次のコマンドで、cp-sample999.txtを削除してください。

```shell
$ rm cp-sample999.txt
```

(10) 次のコマンドで、cp-sample999.txtを削除されたことを確認してください。

```shell
$ ls -alh                           
total 16
drwxr-xr-x@  4 <ユーザー名>  staff   128B Jun 13 09:34 .
drwxr-xr-x  16 <ユーザー名>  staff   512B Jun 13 09:34 ..
-rw-r--r--@  1 <ユーザー名>  staff    15B Jun 13 09:29 cp-sample1.txt
```

# ファイル・フォルダの作成・削除
(1) 次のコマンドでex04/p1/c1フォルダを作成しようとすると、失敗することを確認してください。

```shell
$ mkdir p1/c1
mkdir: p1: No such file or directory
```

> 失敗したのは、c1の親フォルダであるp1がまだ作成されていないからです。

(2) 次のコマンドでex04/p1/c1フォルダを作成してください。

```shell
$ mkdir -p p1/c1
```

> `-p`オプションを付加すると、まだ存在しない親フォルダも作成されます。

(3) 次のコマンドでex04/p1/c1フォルダにsample.txtを作成してください。

```shell
$ touch p1/c1/sample.txt
```

(4) 次のコマンドで、ex04/p1/c1フォルダにsample.txtが作成されたことを確認してください。

```shell
$ ls -alh p1/c1 
total 0
drwxr-xr-x@ 3 <ユーザー名>  staff    96B Jun 13 09:42 .
drwxr-xr-x@ 3 <ユーザー名>  staff    96B Jun 13 09:39 ..
-rw-r--r--@ 1 <ユーザー名>  staff     0B Jun 13 09:42 sample.txt
```

(5) 次のコマンドで、sample.txtがまだ空であることを確認してください。

```shell
$ cat p1/c1/sample.txt

```

(6) 次のコマンドでp1フォルダを削除しようとすると、失敗することを確認してください。

```shell
$ rm p1
rm: p1: is a directory
```

> 失敗したのは、オプション無しのrmコマンドはファイルのみ削除可能だからです。

(7) 次のコマンドでp1フォルダを削除してください。

```shell
$ rm -r p1
```

> `-r`オプションを付加することで、フォルダの削除が可能になります。

(8) 次のコマンドで、p1フォルダが削除されたことを確認してください。

```shell
$ ls -alh
total 8
drwxr-xr-x@  3 <ユーザー名>  staff    96B Jun 13 09:50 .
drwxr-xr-x  16 <ユーザー名>  staff   512B Jun 13 09:51 ..
-rw-r--r--@  1 <ユーザー名>  staff    15B Jun 13 09:29 cp-sample1.txt
```
