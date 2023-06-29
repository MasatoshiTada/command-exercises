mycmdは、mycmd.cをIntel版Mac向けにコンパイルしたものです。

Arm版MacやLinuxで実行したい場合は、次のコマンドでコンパイルしてから実行してください。

```shell
# Intel Mac版mycmdを削除
$ rm mycmd
# 利用している環境向けのmycmdを作成
$ gcc -o mycmd mycmd.c
```
