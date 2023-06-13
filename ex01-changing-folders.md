演習1 フォルダの移動
=================

ex01フォルダの中身は次のようになっています。

```shell
ex01
├── p1
│   ├── c11
│   │   └── sample11.txt
│   └── c12
│       └── sample12.txt
└── p2
    ├── c21
    │   └── sample21.txt
    └── c22
        └── sample22.txt
```

# 相対パスによるフォルダ移動
(1) ターミナルを開いてください。

(2) 次のコマンドで、ex01フォルダに移動してください。

```shell
$ cd ~/command-exercises/ex01
```

(3) 次のコマンドで、カレントフォルダを確認してください。

```shell
$ pwd
/Users/<ユーザー名>/command-exercises/ex01
```

(4) 次のコマンドで、ex01/p1/c11フォルダに移動してください。

```shell
$ cd p1/c11
```

> `cd ./p1/c11`でも同様です。

(5) 次のコマンドで、カレントフォルダを確認してください。

```shell
$ pwd
/Users/<ユーザー名>/command-exercises/ex01/p1/c11
```

(6) 次のコマンドで、ex01/p1/c12フォルダに移動してください。

```shell
$ cd ../c12
```

(7) 次のコマンドで、カレントフォルダを確認してください。

```shell
$ pwd
/Users/<ユーザー名>/command-exercises/ex01/p1/c12
```

(8) 次のコマンドで、ex01/p2/c21フォルダに移動してください。

```shell
$ cd ../../p2/c21
```

(9) 次のコマンドで、カレントフォルダを確認してください。

```shell
$ pwd
/Users/<ユーザー名>/command-exercises/ex01/p2/c21
```

(10) 次のコマンドで、ex01フォルダに移動してください。

```shell
$ cd ../..
```

(11) 次のコマンドで、カレントフォルダを確認してください。

```shell
$ pwd
/Users/<ユーザー名>/command-exercises/ex01
```

# 絶対パスによるフォルダ移動
(1) 次のコマンドで、ex01/p2/c22フォルダに移動してください。

```shell
$ cd /Users/<ユーザー名>/command-exercises/ex01/p2/c22
```

> `cat ~/command-exercises/ex01/p2/c22`でも同様です。

(2) 次のコマンドで、カレントフォルダを確認してください。

```shell
$ pwd
/Users/<ユーザー名>/command-exercises/ex01/p2/c22
```

# 相対パスによるファイル読み込み
(1) 次のコマンドで、カレントフォルダを確認してください。

```shell
$ pwd
/Users/<ユーザー名>/command-exercises/ex01/p2/c22
```

(2) 次のコマンドで、ex01/p2/c22/sample22.txtファイルを読み込んでください。

```shell
$ cat sample22.txt
これはsample22.txtです。
```

> `cat ./sample22.txt`でも同様です。

(3) 次のコマンドで、ex01/p2/c21/sample21.txtファイルを読み込んでください。

```shell
$ cat ../c21/sample21.txt
これはsample21.txtです。
```

(4) 次のコマンドで、ex01/p1/c11/sample11.txtファイルを読み込んでください。

```shell
$ cat ../../p1/c11/sample11.txt
これはsample11.txtです。
```

# 絶対パスによるファイル読み込み
(1) 次のコマンドで、ex01/p1/c11/sample11.txtファイルを読み込んでください。

```shell
$ cat /Users/<ユーザー名>/command-exercises/ex01/p1/c11/sample11.txt
これはsample11.txtです。
```

> `cat ~/command-exercises/ex01/p1/c11/sample11.txt`でも同様です。

# lsによるファイル・フォルダ一覧取得
(1) 次のコマンドで、ex01フォルダに移動してください。

```shell
$ cd /Users/<ユーザー名>/command-exercises/ex01
```

(2) 次のコマンドで、ex01フォルダの中身を確認してください。

```shell
$ ls
p1      p2
```

(3) 次のコマンドで、ex01フォルダの中身の詳細情報を確認してください。

```shell
$ ls -l
total 0
drwxr-xr-x@ 4 <ユーザー名>  staff  128 Jun 12 15:35 p1
drwxr-xr-x@ 4 <ユーザー名>  staff  128 Jun 12 15:35 p2
```

(4) 次のコマンドで、ex01フォルダの中身の詳細情報を確認してください。

```shell
$ ls -alh
total 0
drwxr-xr-x@  4 <ユーザー名>  staff   128B Jun 12 15:35 .
drwxr-xr-x  10 <ユーザー名>  staff   320B Jun 13 08:28 ..
drwxr-xr-x@  4 <ユーザー名>  staff   128B Jun 12 15:35 p1
drwxr-xr-x@  4 <ユーザー名>  staff   128B Jun 12 15:35 p2
```

(5) 次のコマンドで、ex01/p1フォルダの中身の詳細情報を確認してください。

```shell
$ ls -alh p1
total 0
drwxr-xr-x@ 4 <ユーザー名>  staff   128B Jun 12 15:35 .
drwxr-xr-x@ 4 <ユーザー名>  staff   128B Jun 12 15:35 ..
drwxr-xr-x@ 3 <ユーザー名>  staff    96B Jun 12 15:36 c11
drwxr-xr-x@ 3 <ユーザー名>  staff    96B Jun 12 15:37 c12
```

> `ls -alh ./p1`でも同様です。

(6) 次のコマンドで、ex01/p1/c11フォルダの中身の詳細情報を確認してください。

```shell
$ ls -alh p1/c11
total 8
drwxr-xr-x@ 3 <ユーザー名>  staff    96B Jun 12 15:36 .
drwxr-xr-x@ 4 <ユーザー名>  staff   128B Jun 12 15:35 ..
-rw-r--r--@ 1 <ユーザー名>  staff    30B Jun 12 15:36 sample11.txt
```

> `ls -alh ./p1/c11`でも同様です。
