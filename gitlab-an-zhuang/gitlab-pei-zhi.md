# gitlab 配置

* gitlab nginx 配置 目录：`/var/opt/gitlab/nginx/`
* gitlab nginx 静态资源公共目录位置：`/opt/gitlab/embedded/service/gitlab-rails/public`
* gitlab-ctl 配置文件:\``/opt/gitlab/embedded/service/gitlab-rails/gitlab.yml`（这个文件是由gitlab-ctl管理的，如果要配置一些信息，可以修改/etc/gitlab/gitlab.rb），修改这个配置在执行`gitlab-ctl reconfigure` 将被还原。



