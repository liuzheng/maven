# 同济Maven私服
## 介绍

亲爱的小伙伴们，同济的 Maven 库上线咯！为了方便广大同济开发同学，我搭建了一个 Maven 中央库，提供高速稳定的网络和服务，为校内 Maven 使用者提供便捷服务。本 Maven 库是从 官方 同步过来的，因为网络等原因，保持每天一次更新。本 Maven 库使用开源软件 Nexus 搭建，对内镜像链接地址为：  http://maven.gettongji.info/content/groups/public/  。

## 使用

接下来将简单介绍如何在您的项目中使用 Maven，以及使用校内提供的 Maven 服务。

### 1.安装 Maven

如果需要使用到 Maven ，必须首先安装 Maven ， Maven 的下载地址在 [Apache Maven](http://maven.apache.org/) 中有。
下载好 Maven 后，需要简单安装下。将下载的  zip  或者  tar.gz  包解压到需要安装到的目录。 接下简单配置下环境变量：

- 新建环境变量  `M2_HOME`  ,输入值为 Maven 的安装目录。
- 新建环境变量  `M2`  ，输入值为:  `%M2_HOME%\bin`  。
- 将 `M2` 环境变量加入  `Path`  的最后，如：  `;%M2%`  ;。

环境变量就这么简单配置下就可以了。打开命令行窗口输入  `mvn -version`  查看是否正常。

### 2.修改 settings.xml

在 Maven 中使用校内的 Maven 服务还需要简单配置一下 Maven，在 Maven 的安装目录下的 conf 文件下有个  `settings.xml`  文件，接下来我们需要对这个文件做简单的修改，修改前您可以简单**备份**下该文件。 打开  `settings.xml`  文件,按下面内容修改。

    <mirrors>
        <mirror>
            <id>nexus-TJ</id>
            <mirrorOf>*</mirrorOf>
            <name>Nexus TJ</name>
            <url>http://maven.gettongji.info/nexus/content/groups/public/</url>
        </mirror>
    </mirrors>

如果您需要修改 Maven 的默认文件保存路径，需要在 settings.xml 文件中修改如下地方。

    <localRepository>PATH/repo</localRepository>

按照如上修改  `settings.xml`  之后，您就可以在自己的 Maven 中使用 我们 为您提供的 Maven 服务了。
