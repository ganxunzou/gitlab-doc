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



