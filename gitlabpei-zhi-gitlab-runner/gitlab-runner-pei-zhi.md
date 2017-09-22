# gitlab-runner 注册

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

以上是注册gitlab-runner的过程，特别注意最后异步，我选择的是shell，因为我想通过sh脚本处理任务。gitlab-runner支持`share`和 `specific` 两种模式，可以将`share` 改成`specific` ，但是不能将`specific` 改成 `share`

#### 注册共享的gitlab-runner



