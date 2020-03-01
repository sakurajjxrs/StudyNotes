## jdk1.8安装

### 环境变量的配置

安装好jdk以后

```
vim /etc/profile
```

在段落最后输入

```
export JAVA_HOME=/usr/software/java/jdk1.8.0_144
export PATH=$JAVA_HOME/bin:$PATH
export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
```

保存退出

```
source /etc/profile
```

完成配置更新

输入java -version检查版本

## tomcat8.5的安装

### 下载安装包下

下载[tomcat8.5](https://tomcat.apache.org/download-80.cgi),下载core中tar.gz

解压文件

```
tar -zxvf apache-tomcat-8.5.51.tar.gz
```

为了方便以后的操做现在先将解压后的包名修改一下,改成tomcat8

```
mv apache-tomcat-8.5.51 tomcat8
```

### 配置startup.sh

输入 chmod 755 -R apache-tomcat-8.5.40 完成授权

进入startup.sh文中，并在最后加入一下内容

```
export JAVA_HOME=/usr/software/java/jdk1.8.0_144
export JRE_HOME=${JAVA_HOME}/jre
export CLASSPATH=.:%{JAVA_HOME}/lib:%{JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
export TOMCAT_HOME=/usr/software/tomcat8
```