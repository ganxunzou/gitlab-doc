# gitbook CI 配置

gitlab + gitbook 实现持续集成和发布（website）分工如下：

* `gitlab` 负责仓库管理，提供 `commit hook`   
* `gitlab-runner`  负责监听  `commit hook`，然后执行`.gitlab-ci.yml` 脚本

* `.gitlab-ci.yml`  脚本中使用gitbook build 构建书本并输出到nginx 的 public目录

gitbook + gitlab 实现CI配置依赖gitlab-runner。gitlab-runner的安装和注册详见：[gitlab-ci 持续集成配置](/gitlabpei-zhi-gitlab-runner.md)。

#### .gitlab-ci.yml

```
ReleaseBook:
 script:
  - sh ~/ReleaBook.sh
```

#### ReleaseBook.sh

我发布文档的规则：[http://127.0.0.1/doc/ProjectName/index.html](http://127.0.0.1/doc/ProjectName/index.html) ,其中ProjectName是当前项目名。例如，我的文档资源库：git@127.0.0.1:root/testDoc.git ，生成的文档网址：[http://127.0.0.1/doc/testDoc/index.html](http://127.0.0.1/doc/testDoc/index.html)

    p=`pwd`
    echo $p
    bookname="${PWD##*/}"
    echo $bookname
    gitlabPublic="/opt/gitlab/embedded/service/gitlab-rails/public/doc"
    test -d $gitlabPublic && echo $gitlabPublic 'exist' || mkdir $gitlabPublic
    echo $gitlabPublic/$bookname
    gitbook build ./ $gitlabPublic/$bookname

#### nginx location 自动访问目录下的index.html

![](/assets/gitlab-ci-nginx-doc.png)

如上图：gitbook build 生成readme页的网址是：[http://127.0.0.1/doc/testDoc/，而不是http://127.0.0.1/doc/testDoc/index.html。对于这种问题有两种处理方式：](http://127.0.0.1/doc/testDoc/，而不是http://127.0.0.1/doc/testDoc/index.html。对于这种问题有两种处理方式：) 修改gitbook npm库相关源码加上index.html ，或者 让nginx支持访问目录的时候自动访问目录下的index.html文件。当然选择后者。

修改：`/var/opt/gitlab/nginx/conf/gitlab-http.conf` 增加如下配置

```
 location ~ /doc/(.*) {
    root /opt/gitlab/embedded/service/gitlab-rails/public;
    index index.html;
 }
```

然后重启：`gitlab-ctl restart`

