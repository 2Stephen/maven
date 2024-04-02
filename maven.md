# maven

------



## ch-01

1.maven简介：项目管理工具，将项目开发过程抽象成一个项目对象模型（POM）

2.maven的作用：

+ 项目构建：提供标准的、跨平台的自动化项目构建方式
+ 依赖管理：方便快捷的管理项目依赖的资源（jar包），避免资源间的版本冲突问题
+ 统一开发结构：提供标准的、统一的项目结构

## ch-02

1.[maven官网](http://maven.apache.org)

2.[maven下载](http://maven.apache.org/download.cgi)

+ mac安装:`brew install maven`
+ windows安装：官网下载配置变量
+ 验证安装结果：`mvn --version`

## ch-03

1.maven基础概念

+ 1.仓库：用于存储资源，包含各种jar包

  + 仓库分类：
    + 本地仓库：自己电脑上的存储资源的仓库，远程连接仓库获取资源
    + 远程仓库：非本机电脑上的仓库，为本地仓库提供资源
      + 中央仓库：maven团队维护，存储所有资源的仓库
      + 私服：部门/公司范围内存储资源的仓库，从中央仓库获取资源
  + 私服作用：
    + 保存具有版权的资源，包含购买或自主研发的jar包
      + 中央仓库jar包开源
    + 一定范围内共享资源，对内开放，不对外共享

+ 2.坐标：用于描述仓库中资源的位置

  + 主要组成：

    + groupId：定义当前maven项目隶属组织名称（域名反写com.example）
    + artifactId：定义当前maven项目名称（通常模块名称）
    + version：定义当前项目版本号
    + packaging：定义该项目打包方式

    [mvnrepository官网](https://mvnrepository.com)

2.maven仓库配置

+ 默认在.m2位置，修改位置需要在conf/settings.xml修改

+ 镜像仓库配置：conf/settings.xml修改

  ```xml
  <mirror>
        <id>nexus-aliyun</id> 
        <mirrorOf>central</mirrorOf>
        <name>Nexus aliyun</name>
        <url>http://maven.aliyun.com/nexus/content/groups/public</url>
  </mirror>
  ```

  + id：唯一标识符
  + mirrorOf：镜像仓库类型 central中央仓库

## ch-04

1.maven项目框架：

+ src
  + main
    + java
    + resources
  + test
    + java
    + resources
+ pom.xml

2.

