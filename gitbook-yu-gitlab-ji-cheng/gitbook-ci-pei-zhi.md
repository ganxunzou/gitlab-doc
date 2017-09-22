# gitbook CI 配置

gitbook + gitlab 实现CI配置依赖gitlab-runner。gitlab-runner的安装和注册详见：[gitlab-ci 持续集成配置](/gitlabpei-zhi-gitlab-runner.md)

gitlab + gitbook 实现持续集成和发布（website）分工如下：

* gitlab 负责仓库管理，提供commit的hook
* gitlab-runner 负责监听commit hook，然后执行.gitlab-ci.yml 脚本
* .gitlab-ci.yml 脚本中使用gitbook build 构建书本并输出到nginx public目录。
* 


