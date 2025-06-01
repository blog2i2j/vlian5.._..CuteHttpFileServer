       
## 简介 

CuteHttpFileServer/chfs是一个免费的、HTTP协议的文件共享服务器，使用浏览器可以快速访问。它具有以下特点：

* 单个文件，核心功能无需其他文件 
* 跨平台运行，支持主流平台：Windows，Linux和Mac 
* 界面简洁，简单易用 
* 支持扫码下载和手机端访问，手机与电脑之间共享文件非常方便 
* 支持账户权限控制和地址过滤 
* 支持快速分享文字片段 
* 支持webdav协议

与其他常用文件共享方式（如FTP，飞秋，网盘，自己建站）相比，具有使用简单，适用场景更多的优点，在个人使用以及共享给他人的场景中非常方便快捷。




## 下载
#### 命令行程序
[版本更新日志](http://iscute.cn/tar/chfs/3.1/chfs-changelog.txt)

[chfs-linux-386-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-386-3.1.zip) 

[chfs-linux-amd64-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-amd64-3.1.zip) 

[chfs-linux-arm-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-arm-3.1.zip)

[chfs-linux-arm64-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-arm64-3.1.zip) 

[chfs-linux-mips-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-mips-3.1.zip)

[chfs-linux-mips-softfloat-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-mips-softfloat-3.1.zip) 

[chfs-linux-mips64-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-mips64-3.1.zip) 

[chfs-linux-mips64-softfloat-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-mips64-softfloat-3.1.zip) 

[chfs-linux-mips64le-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-mips64le-3.1.zip) 

[chfs-linux-mipsle-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-linux-mipsle-3.1.zip) 

[chfs-mac-386-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-mac-386-3.1.zip) 

[chfs-mac-amd64-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-mac-amd64-3.1.zip)

[chfs-windows-x64-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-windows-x64-3.1.zip)

[chfs-windows-x86-3.1.zip](http://iscute.cn/tar/chfs/3.1/chfs-windows-x86-3.1.zip)

[chfs-支持低版本操作系统(MS XP,OpenBSD 6.0...).zip](http://iscute.cn/tar/chfs/3.1/chfs-支持低版本操作系统(MS，XP,OpenBSD6.0...).zip) 

#### GUI程序
[gui-chfs-windows.zip](http://iscute.cn/tar/chfs/3.1/gui-chfs-windows.zip) 
# 基本用法
#### 非系统服务运行
该程序是一个控制台程序，可直接双击运行，或在控制台/命令行中运行。可通过命令行参数进行相关配置，如使用'chfs --help'来查看帮助：
```sh
usage: chfs.exe []
  -file string
        Configuration file.
  -path string
        Shared directories, separated by '|'. (default ".")
  -port uint
        HTTP listening port. (default 80)
  -version
        Print version.
```

参数说明：
```
help:	显示帮助信息
path:	你要共享的目录，默认为程序运行目录。如果需要共享多个目录，则用“|”符号隔开。注意：如果路径带有空格，则需要将整个路径用引号包住。
port:	程序使用的端口号，默认为80
file:	配置文件，该文件可配置上述配置项，语法相同，如果配置有效则覆盖对应配置项。另外，一些功能需要通过配置文件进行配置，比如页面自定义和SSL证书设置。更详细的说明请参考配置文件：[点击下载](http://iscute.cn/asset/chfs.ini)，请认真参考。
version:	显示程序版本号
```

Tip：在Windows系统中，可以使用右键弹出菜单快捷地共享某个目录。步骤如下：

1, 下载[注册表模板](http://iscute.cn/asset/chfs.reg)文件
2, 在该文件中编辑你的chfs.exe的真实路径，并可添加其他参数
3, 双击该脚本文件，进行注册表添加

## 非系统服务运行GUI
在windows系统中可以直接使用GUI版本，简单易用。

## 以系统服务运行
本程序不是一个服务程序，所以如果你要以系统服务运行，需要自己创建服务。下面给出Windows平台的创建服务方法(通过NSSM工具)：
```
1, 将chfs.exe放在指定目录，假设为：d:\program\cutehttpfileserver
2, 到http://www.nssm.cc/download下载nssm
3, 将解压后的nssm程序放在d:\program\cutehttpfileserver中
4, 在d:\program\cutehttpfileserver中运行命令行，或运行命令行并CD至该目录
5, 假设你的服务名称为cute_http_file_service，命令行中输入：nssm install cute_http_file_service
6, NSSM会弹出配置对话框，在该对话框中输入程序路径以及运行参数
7, 启动服务，命令行中输入：nssm start cute_http_file_service
```
## 高级用法

#### 如何启用webdav？
程序默认支持webdav，跟http共用同一套访问规则。其地址为：[http://host:port/webdav](http://host:port/webdav)


## 测试说明
#### 运行主机
* **Windows XP：**√ 
* **Windows 10：**√ 
* **Debian 9：**√ 
* **CentOS 7：**√ 
* **其他：**未测试 
#### PC浏览器
* **IE：**11+ √ 
* **Edge：**√ 
* **Firefox：**√ 
* **Chrome：**√ 
* **Opera：**√ 
* **Safari：**√ 
* **其他:**未测试 

## 捐助
[捐助地址](https://pay.ods.im/)
