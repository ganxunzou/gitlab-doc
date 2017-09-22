# gitlab nginx 配置

* gitlab nginx 目录：`/var/opt/gitlab/nginx/`

* gitlab nginx 核心配置文件：`/var/opt/gitlab/nginx/conf/nginx.conf`

* gitlab nginx 静态资源公共目录位置：`/opt/gitlab/embedded/service/gitlab-rails/public`

#### 修改nginx配置并生效

修改`nginx.conf`文件后，最好先执行`nginx -t` 的命令测试`nginx.conf` 文件语法是否正确。测试通过后需要执行：`gitlab-ctl restart` 生效配置文件



