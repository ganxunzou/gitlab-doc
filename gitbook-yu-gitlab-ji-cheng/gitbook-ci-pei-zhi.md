# gitbook CI 配置

gitlab + gitbook 实现持续集成和发布（website）分工如下：

* `gitlab` 负责仓库管理，提供`commit hook`
* gitlab-runner 负责监听`commit hook`，然后执行`.gitlab-ci.yml` 脚本

* `.gitlab-ci.yml`  脚本中使用gitbook build 构建书本并输出到nginx 的 public目录

gitbook + gitlab 实现CI配置依赖gitlab-runner。gitlab-runner的安装和注册详见：[gitlab-ci 持续集成配置](/gitlabpei-zhi-gitlab-runner.md)

