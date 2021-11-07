# lisney
look cold and indifferent
>有些同学可能一听到搭建博客就望而却步，弄个博客网站，不得有台服务器吗？不得搞数据库吗？不得注册域名吗？现在交给大家一个不需要这些步骤，就可以快速的免费搭建一个自己的博客，而且还可以使用markdown来直接写文章。一个本人不是一个程序员，也不是专业技术人员，翻遍了好多材料，发现通过Github+hexo可以快速搭建一个自己博客，而且是**免费的**

下面就将我的详细步骤介绍给大家：
# 第一步，注册自己的github账号
- github 注册
 GitHub 是个好东西啊，它提供了 GitHub Pages 帮助我们来架设一个静态网站，这就解决了服务器的问题。GitHub Pages 允许每个账户创建一个名为 {username}.github.io 的仓库，另外它还会自动为这个仓库分配一个 github.io 的二级域名，这就解决了域名的问题，当然如果想要自定义域名的话，也可以支持。所以说，基本上，先注册个 GitHub 账号就能搞了。
注册网址[：https://github.com/](https://github.com/)

![1.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/88d8233ba2514c1ab05851be2c56bf24~tplv-k3u1fbpfcp-watermark.image?)

- github新建一个仓库（repository)
首先在 GitHub 新建一个仓库（Repository），名称为 {username}.github.io，注意这个名比较特殊，必须要是 github.io 为后缀结尾的。比如 NightTeam 的 GitHub 用户名就叫 NightTeam，那我就新建一个 nightteam.github.io，新建完成之后就可以进行后续操作了。另外如果 GitHub 没有配置 SSH 连接的建议配置一下，这样后面在部署博客的时候会更方便。
# 安装 Node.jss程序

首先在自己的电脑上安装 Node.js，[下载地址](https://nodejs.org/zh-cn/download/)：，可以安装 Stable 版本。安装完毕之后，确保环境变量配置好，能正常使用 npm 命令。下面我们来正式开始吧。

![2.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/7d90ade5189147779fd869969ddec4e9~tplv-k3u1fbpfcp-watermark.image?)

#安装git
-   [git下载地址](https://git-scm.com/downloads/)
-   下载git安装文件，双击执行安装。按照顺序安装即可。
完成之后，可以运行git在windows中会出现个类似于命令行的界面：

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/2a770ee8bf784bfa9b2232aaf07a90b6~tplv-k3u1fbpfcp-watermark.image?)

# 安装 Hexo
- 在git 命令行运行命令: `npm install -g hexo-cli`
接下来就需要安装 Hexo 了，这是一个博客框架，Hexo 官方还提供了一个命令行工具，用于快速创建项目、页面、编译、部署 Hexo 博客，所以在这之前我们需要先安装 Hexo 的命令行工具。
命令如下：

npm install -g hexo-cli

安装完毕之后，确保环境变量配置好，能正常使用 hexo 命令。
# 通过hexo加载个本地网站
接下来我们使用 Hexo 的命令行创建一个项目，并将其在本地跑起来，整体跑通看看。

首先使用如下命令创建项目：

hexo init {name}

这里的 name 就是项目名，我这里要创建 lisney 的博客，我就把项目取名为 lisney 了，用了纯小写，命令如下：
![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8772db04c5fd4741af44f202f988d598~tplv-k3u1fbpfcp-watermark.image?)

`hexo init lisney` 

这样 lisney 文件夹下就会出现 Hexo 的初始化文件，包括 themes、scaffolds、source 等文件夹，这些内容暂且先不用管是做什么的，我们先知道有什么，然后一步步走下去看看都发生了什么变化。

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/967fd9395d4d49088c94a241d1a7b8ae~tplv-k3u1fbpfcp-watermark.image?)


接下来我们首先进入新生成的文件夹里面，然后调用 Hexo 的 generate 命令，将 Hexo 编译生成 HTML 代码，命令如下：

`hexo generate` 

可以看到输出结果里面包含了 js、css、font 等内容，并发现他们都处在了项目根目录下的 public 文件夹下面了。

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/9dfbd8c7ce2b4bf2896a7426caaa5749~tplv-k3u1fbpfcp-watermark.image?)
然后我们利用 Hexo 提供的 serve 命令把博客在本地运行起来，命令如下：

`hexo serve`

运行之后命令行输出如下：

INFO Start processingINFO Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.

![image.png](https://p6-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/63c248fe48344569a09ce8b3bfdf67cf~tplv-k3u1fbpfcp-watermark.image?)

它告诉我们在本地 4000 端口上就可以查看博客站点了，如图所示：

![image.png](https://p1-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/d9279821e0584eeb96fe3c83e069f0d8~tplv-k3u1fbpfcp-watermark.image?)
看到这个页面，咱们的搭建平台的PC端的工作基本就完成了。

# 正式部署网站
这样一个博客的架子就出来了，我们只用了三个命令就完成了。
接下来我们来将这个初始化的博客进行一下部署，放到 GitHub Pages 上面验证一下其可用性。成功之后我们可以再进行后续的修改，比如修改主题、修改页面配置等等。
那么怎么把这个页面部署到 GitHub Pages 上面呢，其实 Hexo 已经给我们提供一个命令，利用它我们可以直接将博客一键部署，不需要手动去配置服务器或进行其他的各项配置。
部署命令如下：

`hexo deploy
` 
在部署之前，我们需要先知道博客的部署地址，它需要对应 GitHub 的一个 Repository 的地址，这个信息需要我们来配置一下。

打开根目录下的 _config.yml 文件，找到 Deployment 这个地方，把刚才新建的 Repository 的地址贴过来，然后指定分支为 master 分支，最终修改为如下内容：

`Deployment
 Docs: https://hexo.io/docs/deployment.html
 
 deploy: 
 
 type: git 
 
 repo: {git repo ssh address} 
 
 branch: master`

我的就修改为如下内容：

`Deployment## Docs: https://hexo.io/docs/deployment.html

deploy:

type: git 
repo: git@github.com:https://github.com/lechurry/lisney.git 

branch: master`

> 编辑在liunx下可以使用vim，在windows下，可以用windows目录下的 文本编辑器。（找到_config.yml 的目录，用文本编辑器打开）

# 安装支持git部署的插件

另外我们还需要额外安装一个支持 Git 的部署插件，名字叫做 hexo-deployer-git，有了它我们才可以顺利将其部署到 GitHub 上面，如果不安装的话，在执行部署命令时会报如下错误：

Deployer not found: git

好，那就让我们安装下这个插件，在项目目录下执行安装命令如下：

npm install hexo-deployer-git --save

安装成功之后，执行部署命令：

# 运营 hexo deploy
在命令行下
hexo deploy
运行结果类似如下：

INFO Deploying: gitINFO Clearing .deploy_git folder...INFO Copying files from public folder...INFO Copying files from extend dirs...On branch masternothing to commit, working directory cleanCounting objects: 46, done.Delta compression using up to 8 threads.Compressing objects: 100% (36/36), done.Writing objects: 100% (46/46), 507.66 KiB | 0 bytes/s, done.Total 46 (delta 3), reused 0 (delta 0)remote: Resolving deltas: 100% (3/3), done.To git@github.com:NightTeam/nightteam.github.io.git * [new branch] HEAD -> masterBranch master set up to track remote branch master from git@github.com:NightTeam/nightteam.github.io.git.INFO Deploy done: git

如果出现类似上面的内容，就证明我们的博客已经成功部署到 GitHub Pages 上面了，这时候我们访问一下 GitHub Repository 同名的链接，比如我的 NightTeam 博客的 Repository 名称取的是 nightteam.github.io，那我就访问 http://nightteam.github.io，这时候我们就可以看到跟本地一模一样的博客内容了。
