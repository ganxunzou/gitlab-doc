# gitlab-runner 注册

[https://docs.gitlab.com/runner/register/index.html](https://docs.gitlab.com/runner/register/index.html)

```
-bash-4.2# gitlab-runner register
Running in system-mode.                            

Please enter the gitlab-ci coordinator URL (e.g. https://gitlab.com/):
http://127.0.0.1
Please enter the gitlab-ci token for this runner:
ggADrYkwz5e1M9wEyWDv

Please enter the gitlab-ci description for this runner:
test-runner
Please enter the gitlab-ci tags for this runner (comma separated):
test-runner
Whether to run untagged builds [true/false]:
Whether to lock Runner to current project [true/false]:
[false]: 
Registering runner... succeeded                     runner=ggADrYkw
Please enter the executor: parallels, virtualbox, docker-ssh+machine, docker, docker-ssh, shell, ssh, docker+machine, kubernetes:
shell
Runner registered successfully. Feel free to start it, but if it's running already the config should be automatically reloaded! 
-bash-4.2#
```

以上是注册gitlab-runner的过程，特别注意最后异步，我选择的是shell，因为我想通过sh脚本处理任务。gitlab-runner支持`share`和 `specific` 两种模式，可以将`share` 改成`specific` ，但是不能将`specific` 改成 `share` 。可以在注册的时候直接注册 `share` 或`specific` 类型的gitlab-runner，取决于注册时输入的`gitlab-ci token`;

两种模式：

* `share` 所有配置了`.gitlab-ci.yml` 的项目都会被被执行

* `specific` 只针对指定项目有效

#### 注册 share 的gitlab-runner

注册共享的gitlab-runner使用的token是全局的token，通过Admin Area -&gt; Overview -&gt; Runners 可以获取。![](/assets/gitlab-runner-share2.png)

#### 注册 specific 的gitlab-runner

![](/assets/gitlab-runner-specific.png)

#### 将share转成specific

选择share的runner编辑选择对应的项目，点“Enable”按钮

![](/assets/gitlab-runner-share-specific.png)

#### 使用gitlab-ci

在项目根目录配置`.gitlab-ci.yml` ，因为我选择的shell模式，所以我可以在`gitlab-ci.yml` 中写shell命令。助注意语法，可以先验证一下：[http://127.0.0.1/ci/lint](http://127.0.0.1/ci/lint) （127.0.0.1是你服务器的ip）

```
ReleaseBook:
 script:
  - sh ~/ReleaBook.sh
```



