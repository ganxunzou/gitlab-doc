# gitlab email 服务

gitlab默认是开启邮件服务的。详见：`/opt/gitlab/embedded/service/gitlab-rails/config/gitlab.yml`。

```
# Email settings

email_enabled:true
```

因此如果你服务器有默认的邮件服务:`SendMail`或者`postfix`，在修改用户密码，分配用户角色等操作的时候都会通知到用户，不过邮箱默认识别为垃圾邮件

![](/assets/2017-09-15_135136.png)

如果自己的服务器上没有email 服务器，又不想搭建 email 服务器，可以使用SMTP的方式。详见：[SMTP配置](/gitlab-email-fu-wu/smtp-pei-zhi.md)



#### 邮件信息配置

修改：`/etc/gitlab/gitlab.rb` 文件

```
### Email Settings
gitlab_rails['gitlab_email_enabled'] = true
gitlab_rails['gitlab_email_from'] = 'xunzou.gan@conivision.com'
gitlab_rails['gitlab_email_display_name'] = 'ganxunzou'
gitlab_rails['gitlab_email_reply_to'] = 'ganxunzou'
# gitlab_rails['gitlab_email_subject_suffix'] = ''
```



