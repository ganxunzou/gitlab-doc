# Q&A

#### 403 Forbidden while accessing

```bash
error: The requested URL returned error:403 Forbidden while accessing http://gitlab-ci-token:xxxxxxxxxxxxxxxxxx@127.0.0.1/ganxz/testDoc.git/info/refs
```

这个问题是因为gitbook 自动构建`clone`资源库的方式采用的是`http`方式，而当前gitlab的`http`方式被禁用了。解决方案开启`HTTP` 模式的`clone`

![](/assets/gitbook-qa-403.png)

