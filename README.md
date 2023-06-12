# at
Docker environment for Atcoder contests(pypy). Using atcoder-cli.

## Usage
### Build the image
```bash
$ docker build https://github.com/htomy125/at.git#main
```

### Run docker container
```bash
$ docker run -it --rm <repo:tag>
```
### login
```bash
[container]$ acc login
or
[container]$ accl  ## alias
```

```bash
[container]$ oj login https://atcoder.jp/
or
[container]$ ojl  ## alias
```

### Show config directory

```bash
[container]$ acc config-dir
```

### Crate contest directory

```bash
[container]$ acc new <contest-id> --template python
```

### Test the program

```bash
[container]$ cd <task-dir>
[container]$ oj test -c 'python main.py' -d tests
```

### Set Default Lang

```bash
[container]$ acc s main.py -- --guess-python-interpreter pypy
```

### Submit

```bash
[container]$ acc submit
```

## Reference

* [atcoder-cli.git](https://github.com/Tatamo/atcoder-cli.git)
* [Windows 10 上で atcoder-cli を online-judge-tools と連携させて使う：導入からテストと提出までの基本的操作](https://hamukichi.hatenablog.jp/entry/2020/06/02/225148)
* [atcoder-cli インストールガイド](http://tatamo.81.la/blog/2018/12/07/atcoder-cli-installation-guide)
* [atcoder-cliのデフォルト提出言語をPyPy3に設定する](https://foolish-pine.com/2022/09/acc-default-pypy/)
* [そもそもnpmからわからない](https://zenn.dev/antez/articles/a9d9d12178b7b2)
* [nvmとは何か？Node.jsのインストールと最新の安定版にアップデートする方法｜バージョン指定と変更（npm）](https://prograshi.com/framework/nodejs/nvm-install-update-node/)
* [リリース一覧-io.js & Node.js](https://nodejs.org/ja/download/releases/)
* [Node.js for Oracle Linux](https://yum.oracle.com/oracle-linux-nodejs.html)
* [Remote Development with Linux](https://code.visualstudio.com/docs/remote/linux)

