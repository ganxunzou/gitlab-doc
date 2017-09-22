# gitlab 安装

#### 准备环境

* CentOS7

#### 在线安装

[https://about.gitlab.com/installation/\#centos-7](https://about.gitlab.com/installation/#centos-7)

* 安装 HTTP 和 SSH 依赖

```
sudo yum install -y curl policycoreutils openssh-server openssh-clients
sudo systemctl enable sshd
sudo systemctl start sshd
sudo firewall-cmd --permanent --add-service=http
sudo systemctl reload firewalld
```

* 安装postfix邮件服务器（选填）

如果想要使用邮件服务，又不想自己搭建邮件服务器（postfix），可以使用gitlab自带STMP服务。后面会讲

```
sudo yum install postfix
sudo systemctl enable postfix
sudo systemctl start postfix
```

* 在线安装需要添加yum源

```
curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
```

* yum安装

```
sudo yum install -y gitlab-ce
```

* 配置和启动gitlab

```
sudo gitlab-ctl reconfigure
```

* 大功告成，在浏览器访问

在浏览器中输入服务器IP或者域名，gitlab默认使用的nginx做静态资源服务器和反向代理服务器。nginx默认监听的是80端口。因此直接访问ip或者域名会到登陆界面。

---

#### 离线安装

[http://docs.gitlab.com/omnibus/manual\_install.html](http://docs.gitlab.com/omnibus/manual_install.html)，我们主要安装CE版本（社区版）[https://packages.gitlab.com/gitlab/gitlab-ce](https://packages.gitlab.com/gitlab/gitlab-ce)



