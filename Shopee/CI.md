
## 前端部署


如果我要部署自己的博客，一般需要以下几步：

1. 使用 webpack 编译代码，产出静态资源
2. 打开 FTP 软件，上传替换文件
3. 看看网站是否在线上工作正常
4. 将本地代码提交


随之而来的问题：

1. 手动部署成本太高
2. 需要手动维护环境
3. 难以排查线上问题



## 虚拟机

一般是通过某种软件来实现，仿真出一台或者多台计算机的各种硬件，这就是虚拟机。

用户可以在这一台虚拟机上安装、运行操作系统和各种应用，解决了环境不一致的问题。


![image](../assets/images/VM.jpg)


缺点：
1. 资源占用多
2. 冗余步骤多
3. 启动慢



## Docker

在一艘大船上，可以把货物放到集装箱中，集装箱彼此之间不会互相影响。

这样就不需要专门装水果的船和专门装化学品的船了。

只要这些货物在集装箱里封装的好好的，那我就可以用一艘大船把他们都运走。


![docker](../assets/images/docker.jpeg)


Docker 是一个开源的应用容器引擎，基于 Go 语言 并遵从 Apache2.0 协议开源。

Docker 可以让开发者打包他们的应用以及依赖包到一个轻量级、可移植的容器中，然后发布到任何流行的 Linux 机器上，也可以实现虚拟化。


![docker](../assets/images/dockerVSvm.png)


Docker 技术的三大核心概念，分别是：

1. 镜像（Image）
2. 容器（Container）
3. 仓库（Repository）


## 镜像


## 容器



## 什么是 CI/CD？


工厂里的装配线以快速、自动化、可重复的方式从原材料生产出消费品。

同样，软件交付以快速、自动化和可重复的方式从源代码生成发布版本。


如何完成这项工作的总体设计称为“持续交付”（CD）。

启动装配线的过程称为“持续集成”（CI）。


确保质量的过程称为“持续测试”，将最终产品提供给用户的过程称为“持续部署”。

一些专家让这一切简单、顺畅、高效地运行，这些人被称为运维开发 DevOps 践行者。


## 持续

持续不是指“一直在进行”，而是“随时可进行”，一般来说包括这几个方面：

- 频繁发布
- 自动化流程
- 可重复
- 快速迭代


## 什么是持续交付管道

将源代码转换为可发布产品的多个不同的任务 task 和作业 job 通常串联成一个软件“管道”，一个自动流程成功完成后会启动管道中的下一个流程。

这些管道有许多不同的叫法，例如持续交付管道、部署管道和软件开发管道。

大体上讲，程序管理者在管道执行时管理管道各部分的定义、运行、监控和报告。


![image](../assets/images/CI.jpg)



## Webhook

> Events are at the core of webhooks. These webhooks fire whenever a certain action is taken on the repository, which your server's payload URL intercepts and acts upon.


Webhook 简单来说就是一种反向 API 机制，是在特定情况下触发的一种 API，类似于触发器。

![Webhook](../assets/images/webhook.png)


Github 的 Webhook：

![Github Webhook](../assets/images/github.png)



## Travis CI

Travis CI 提供的是持续集成服务（Continuous Integration，简称 CI）。

它绑定 Github 上面的项目，只要有新的代码，就会自动抓取。

然后，提供一个运行环境，执行测试，完成构建，还能部署到服务器。


![Travis CI](../assets/images/travis.png)


Travis 要求项目的根目录下面，必须有一个.travis.yml文件。

这是配置文件，指定了 Travis 的行为。

一般有下面几个阶段：

1. 安装依赖阶段
2. 运行脚本阶段
3. 部署阶段（非必须）


![demo](../assets/images/carbon.png)



## Github Actions


持续集成由很多操作组成，比如抓取代码、运行测试、登录远程服务器，发布到第三方服务等等。

GitHub 把这些操作就称为 actions。


GitHub 提供了[官方市场](https://github.com/marketplace?type=actions)，允许开发者把每个操作写成独立的脚本文件，存放到代码仓库，使得其他开发者可以引用。

整个持续集成过程，就变成了一个 actions 的组合。


使用 Github Actions 在这个仓库的 .github/workflows 目录，生成一个 workflow 文件，也是 `yaml` 语法。


GitHub Actions 有一些自己的术语。

1. workflow：持续集成一次运行的过程，就是一个 workflow。

2. job：一个 workflow 由一个或多个 jobs 构成，含义是一次持续集成的运行，可以完成多个任务。

3. step：每个 job 由多个 step 构成，一步步完成。

4. action：每个 step 可以依次执行一个或多个命令（action）。


![actions](../assets/images/actions.png)


![action-log](../assets/images/action-log.png)


## Jenkins



## Jenkins 流水线（pipeline）

Pipeline，简而言之，就是一套运行于Jenkins上的工作流框架。

将原本独立运行于单个或者多个节点的任务连接起来，实现单个任务难以完成的复杂流程编排与可视化。

![jenkins_pipeline](../assets/images/jenkins.png)


