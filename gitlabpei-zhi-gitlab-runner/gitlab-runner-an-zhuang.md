# [gitlab-runner 配置](/gitlabpei-zhi-gitlab-runner/gitlab-runner-pei-zhi.md)gitlab-runner 安装

#### 在线安装

[https://docs.gitlab.com/runner/install/](https://docs.gitlab.com/runner/install/)，我的系统的CentOS7：[https://docs.gitlab.com/runner/install/linux-repository.html](https://docs.gitlab.com/runner/install/linux-repository.html)

* 添加gitlab 官方的yum源

```
curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.rpm.sh | sudo bash
```

* yum安装gitlab-runner

```
sudo yum install gitlab-runner
```

* [gitlab-runner 配置](/gitlabpei-zhi-gitlab-runner/gitlab-runner-pei-zhi.md)

#### 离线安装

[https://packages.gitlab.com/runner/gitlab-runner](https://packages.gitlab.com/runner/gitlab-runner) 下载gitlab-ci-multi-runner-9.5.0-1.x86\_64.rpm，然后拷贝到服务器手动执行

```
rpm -i gitlab-ci-multi-runner-9.5.0-1.x86_64.rpm
```

[gitlab-runner 配置](#)

