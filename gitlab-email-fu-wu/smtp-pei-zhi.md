# SMTP 邮件代理配置

gitlab 所在服务器没有email服务，但是有共用的邮件服务器（eg: [http://mail.qq.com](http://mail.qq.com)），想使用公共的邮件服务器代理邮件的发送和接受，这时候就可以用gitlab 提供的SMTP服务。

* 开启SMTP配置

修改配置文件:`/etc/gitlab/gitlab.rb` （官方的详细配置教程：[https://docs.gitlab.com/omnibus/settings/smtp.html\#qq-exmail](https://docs.gitlab.com/omnibus/settings/smtp.html#qq-exmail)）

```
gitlab_rails['smtp_enable'] = true
gitlab_rails['smtp_address'] = "smtp.exmail.qq.com"
gitlab_rails['smtp_port'] = 465
gitlab_rails['smtp_user_name'] = "xxxx@xx.com"
gitlab_rails['smtp_password'] = "password"
gitlab_rails['smtp_authentication'] = "login"
gitlab_rails['smtp_enable_starttls_auto'] = true
gitlab_rails['smtp_tls'] = true
gitlab_rails['gitlab_email_from'] = 'xxxx@xx.com'
```

这里需要注意 `gitlab_rails['smtp_tls']` 属性的配置。总结来说：如果 `gitlab_rails['smtp_port']` 端口是`465` 需要配置成：`gitlab_rails['smtp_tls']=true` ，如果端口是`25` 需要配置成： `gitlab_rails['smtp_tls']=false`

* 测试发送邮件

[https://docs.gitlab.com/ce/administration/troubleshooting/debug.html](https://docs.gitlab.com/ce/administration/troubleshooting/debug.html)



