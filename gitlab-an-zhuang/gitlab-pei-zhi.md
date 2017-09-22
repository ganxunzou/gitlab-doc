# gitlab 相关配置

#### gitlab 相关配置文件和目录

* gitlab-ctl 配置文件:`/opt/gitlab/embedded/service/gitlab-rails/gitlab.yml`（这个文件是由gitlab-ctl管理的，如果要配置一些信息，可以修改/etc/gitlab/gitlab.rb），修改这个配置在执行`gitlab-ctl reconfigure` 将被还原。
* gitlab 核心配置文件：`/etc/gitlab/gitlab.rb`

#### 修改服务器url

* 修改：`/etc/gitlab/gitlab.rb`

```
external_url 'http://127.0.0.1'
```

* 执行`gitlab-ctl reconfigure` 生效配置文件

#### gitlab-ctl 常用命令

* `gitlab-ctl reconfigure`：修改核心配置文件需要生效时执行
* `gitlab-ctl start` ：启动gitlab
* `gitlab-ctl stop` ：关闭gitlab
* `gitlab-ctl restart` ：重启gitlab

#### [gitlab nginx 配置](/gitlab-an-zhuang/gitlab-pei-zhi/gitlab-nginx.md)



