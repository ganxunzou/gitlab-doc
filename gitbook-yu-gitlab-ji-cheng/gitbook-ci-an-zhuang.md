# gitbook-cli安装

gitbook 依赖node环境。此处忽略node的安装过程。

#### 在线安装

* 安装gitbook-cli

```
npm i -g gitbook-ci
```

* 安装gitbook库

`gitbook-cli` 构建书本需要依赖`gitbook` 库。可以在任意目录中创建一本书：含README.md的文件夹，执行`gitbook build` 命令进行构建会自动下载`gitbook` 库，默认情况下，gitbook下载后保存本地的路径是：`~/.gitbook`

#### 离线安装

离线安装需要先准备好资源，可以找一台可以联网的机子执行一遍：在线安装，然后拷贝资源。离线安装有很多知识点的整合需要详细看以下步骤。

* 离线全局（-g）安装`gitbook-cli` 库  

离线安装gitbook-cli需要知道当前系统的node安装前置路径。先通过：`npm config ls -l` 查看去全量的npm配置文件，找到`prefix` ，我CentOS7的`prefix="/usr"` 。

1. 获取gitbook-cli库

```
#注意用户目录
window:
   C:\Users\Administrator\AppData\Roaming\npm\node_modules\gitbook-cli


# 我的prefix = "/usr"
linux:
   /usr/lib/node_modules/gitbook-cli
```

1. 离线安装gitbook-cli

拷贝gitbook-cli的离线资源，解压到相对的目录。

```
#注意用户目录，（特别注意记得拷贝上层目录的gitbook-cli.cmd文件）
window:
   C:\Users\Administrator\AppData\Roaming\npm\node_modules\gitbook-cli


# 我的prefix = "/usr"
linux:
  1. 拷贝资源到： /usr/lib/node_modules/gitbook-cli
  2. 创建快捷方式： ln -s /usr/lib/node_modules/gitbook-cli/bin/gitbook.js /usr/bin/gitbook
```

以上gitbook-cli就算安装结束了，在命令行中执行`gitbook` 命令，有以下输出就算完成了。

```
-bash-4.2# gitbook
CONFIG_ROOT/root

  Usage: gitbook [options] [command]


  Options:

    -v, --gitbook [version]  specify GitBook version to use
    -d, --debug              enable verbose error
    -V, --version            Display running versions of gitbook and gitbook-cli
    -h, --help               output usage information


  Commands:

    ls                        List versions installed locally
    current                   Display currently activated version
    ls-remote                 List remote versions available for install
    fetch [version]           Download and install a <version>
    alias [folder] [version]  Set an alias named <version> pointing to <folder>
    uninstall [version]       Uninstall a version
    update [tag]              Update to the latest version of GitBook
    help                      List commands for GitBook
    *                         run a command with a specific gitbook version
-bash-4.2#
```

* 离线安装gitbook库

离线安装gitbook比较简单，拷贝已经在线安装过的`~/.gitbook` 整个目录到需要离线安装的用户`~/.gitbook` 即可。这里特别注意一下gitlab-runner对应的用户目录`~` 是 `/home/gitlab-runner`



