# gitlab-ci 配置gitlab-runner

gitlab是Go中官方GitLab Runner的存储库。它运行测试并将结果发送给GitLab。 GitLab CI是GitLab包含的开源持续集成服务，用于协调测试。该项目的旧名称是GitLab CI Multi Runner，但请从现在开始使用“GitLab Runner”（内部不在集成CI，CI由gitlab-ci提供服务）。

在没有gitlab-ci之前的做法是：gitlab + jenkins + gitlab-runner。可以类比现在比较流行的：github +  travis + karma ，gitlab-runner和karam是一样的都是runner。

![](/assets/import.png)

我个人喜欢吧gitlab-runner比喻成插排，每个需要持续集成的repos比作灯泡，吧.gitlab-ci.yml比喻成插头电线。一个插排不管有没有插头链接始终都是带电的（runner是一直在跑的），一个插排有多个插座可以链接多个灯泡（runner可以配置多个需要持续集成的repos），灯泡可以选择通电或者不通电，不影响灯泡本身，如果想通电配置一条插头电线（.gitlab-ci.yml）。

#### gitlab-runner 安装



