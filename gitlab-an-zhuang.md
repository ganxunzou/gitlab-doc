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

* 




