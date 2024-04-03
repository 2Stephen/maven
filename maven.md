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
  + mirrorOf：镜像仓库类型 其中central为中央仓库

## ch-04

1.maven项目框架：

+ src
  + main //编写主程序
    + java
    + resources
  + test //测试用
    + java
    + resources
+ pom.xml //存放配置信息

2.maven dos命令

+ mvn compile //编译mvn程序，编译主程序为class字节码文件
+ mvn clean //清理编译完成的文件
+ mvn test //测试用，测试后生成测试报告
+ mvn package //打包用。会先执行编译，再测试，后打包
+ mvn install //将打包后的jar包安装于maven仓库

## ch-05

1.插件创建工程

```bash
mvn archetype:generate
	-DgroupId={project-packaging}
	-DartifactId={project-name}
	-DarchetypeArtifactId=maven-archetype-quickstart
	-DinteractiveMode=false
```

+ DarchetypeArtifactId可选：
  + maven-archetype-quickstart：java项目
  + maven-archetype-webapp：web项目，比Java项目多web目录，且打包方式为war

2.idea创建工程

idea已经集成maven，无需复杂操作

在maven archetype中选择quickstart即可

