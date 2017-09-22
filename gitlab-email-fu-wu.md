# gitlab email 服务

gitlab默认是开启邮件服务的。详见：`/opt/gitlab/embedded/service/gitlab-rails/config/gitlab.yml`。

```
# Email settings

email_enabled:true
```

因此如果你服务器有默认的邮件服务:`SendMail`或者`postfix`，在修改用户密码，分配用户角色等操作的时候都会通知到用户，不过邮箱默认识别为垃圾邮件

![](/assets/2017-09-15_135136.png)





