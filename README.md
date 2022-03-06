### 汉化进度 20%
# 关于

Calibre-Web 是一个 Web 应用程序，它提供了一个干净的界面，用于使用现有的 [Calibre](https://calibre-ebook.com) 数据库浏览、阅读和下载电子书。 

[![GitHub License](https://img.shields.io/github/license/janeczku/calibre-web?style=flat-square)](https://github.com/janeczku/calibre-web/blob/master/LICENSE)
[![GitHub commit activity](https://img.shields.io/github/commit-activity/w/janeczku/calibre-web?logo=github&style=flat-square&label=commits)]()
[![GitHub all releases](https://img.shields.io/github/downloads/janeczku/calibre-web/total?logo=github&style=flat-square)](https://github.com/janeczku/calibre-web/releases)
[![PyPI](https://img.shields.io/pypi/v/calibreweb?logo=pypi&logoColor=fff&style=flat-square)](https://pypi.org/project/calibreweb/)
[![PyPI - Downloads](https://img.shields.io/pypi/dm/calibreweb?logo=pypi&logoColor=fff&style=flat-square)](https://pypi.org/project/calibreweb/)
[![Discord](https://img.shields.io/discord/838810113564344381?label=Discord&logo=discord&style=flat-square)](https://discord.gg/h2VsJ2NEfB)

*该软件是[库](https://github.com/mutschler/calibreserver)的一个分支，并在 GPL v3 许可下获得许可。*
![Main screen](https://github.com/janeczku/calibre-web/wiki/images/main_screen.png)

## 特点

- Bootstrap 3 HTML5 界面
- 完整的图形设置
- 具有详细的每用户权限的用户管理
- 管理界面
- 巴西语、捷克语、荷兰语、英语、芬兰语、法语、德语、希腊语、匈牙利语、意大利语、日语、高棉语、波兰语、俄语、简体和繁体中文、西班牙语、瑞典语、土耳其语、乌克兰语的用户界面
- 用于电子书阅读器应用程序的 OPDS 提要
- 按标题、作者、标签、系列和语言过滤和搜索
- 创建自定义图书收藏（书架）
- 支持编辑电子书元数据和从 Calibre 库中删除电子书
- 支持通过 Calibre 二进制文件转换电子书
- 限制登录用户下载电子书
- 支持匿名用户注册
- 单击按钮即可将电子书推送到 Kindle 设备
- 通过 Calibre-Web 将您的 Kobo 设备与您的 Calibre 库同步
- 支持在浏览器中直接阅读电子书（.txt、.epub、.pdf、.cbr、.cbt、.cbz、.djvu）
- 上传多种格式的新书，包括音频格式（.mp3、.m4a、.m4b）
- 支持口径自定义列 (机翻)
- 能够根据每个用户的类别和自定义列内容隐藏内容
- 可升级程序
- “魔法链接”登录，轻松登录电子书阅读器
- 通过 LDAP、google/github oauth 和代理身份验证登录

## 如何安装

#### 通过pip安装（推荐(๑•̀ㅂ•́)و✧）
1. 使用命令 `pip install calibreweb` 通过 pip 安装 calibre web（根据你的操作系统和/或发行版，命令也可以是`pip3`）。
2. 可选功能也可以通过pip安装，详情请参考 [这里](https://github.com/janeczku/calibre-web/wiki/Dependencies-in-Calibre-Web-Linux-Windows) 来安装 。
3. 安装好后可在终端输入 `cps` 或 `python3 -m cps` 来启动 Calibre-Web 啦！ 

#### 手动安装
1. 通过运行`pip3 install --target vendor -r requirements.txt` (python3.x) 安装依赖项。 或者设置一个python虚拟环境。 
2. 执行命令：`python3 cps.py`（或`nohup python3 cps.py` - 如果你想关闭终端窗口，推荐使用） 

Ubuntu 的问题：
请注意，在某些版本的 Ubuntu 上运行上述安装命令可能会失败，提示 `"can't combine user with prefix"`. 这是一个已知[BUG](https://github.com/pypa/pip/issues/3826)，可以通过使用命令  `pip install --system --target vendor -r requirements.txt` 来解决.

## 快速开始

在浏览器打开 `http://localhost:8083` 或者 `http://localhost:8083/opds` 用于OPDS目录
设置 `Location of Calibre database(Calibre数据库的位置)` 要找到Calibre库（metadata.db）所在文件夹的路径，请按 "submit" 按钮\也可以选择使用Google Drive来托管calibre库 [-> 使用Google Drive](https://github.com/janeczku/calibre-web/wiki/Configuration#using-google-drive-integration)


#### 默认管理员登录:
*用户名:* admin\
*密码:* admin123

## 环境需求

python 3.5+

Optionally, to enable on-the-fly conversion from one ebook format to another when using the send-to-kindle feature, or during editing of ebooks metadata:

[Download and install](https://calibre-ebook.com/download) the Calibre desktop program for your platform and enter the folder including program name (normally /opt/calibre/ebook-convert, or C:\Program Files\calibre\ebook-convert.exe) in the field "calibre's converter tool" on the setup page.

[Download](https://github.com/pgaskin/kepubify/releases/latest) Kepubify tool for your platform and place the binary starting with `kepubify` in Linux: `\opt\kepubify` Windows: `C:\Program Files\kepubify`.

## Docker Images

A pre-built Docker image is available in these Docker Hub repository (maintained by the LinuxServer team):

#### **LinuxServer - x64, armhf, aarch64**
+ Docker Hub - [https://hub.docker.com/r/linuxserver/calibre-web](https://hub.docker.com/r/linuxserver/calibre-web)
+ Github - [https://github.com/linuxserver/docker-calibre-web](https://github.com/linuxserver/docker-calibre-web)
+ Github - (Optional Calibre layer) - [https://github.com/linuxserver/docker-calibre-web/tree/calibre](https://github.com/linuxserver/docker-calibre-web/tree/calibre) 

   This image has the option to pull in an extra docker manifest layer to include the Calibre `ebook-convert` binary.  Just include the environmental variable `DOCKER_MODS=linuxserver/calibre-web:calibre` in your docker run/docker compose file. **(x64 only)**
  
   If you do not need this functionality then this can be omitted, keeping the image as lightweight as possible.
    
   Both the Calibre-Web and Calibre-Mod images are rebuilt automatically on new releases of Calibre-Web and Calibre respectively, and on updates to any included base image packages on a weekly basis if required.
   + The "path to convertertool" should be set to `/usr/bin/ebook-convert`
   + The "path to unrar" should be set to `/usr/bin/unrar`

# Contact

Just reach us out on [Discord](https://discord.gg/h2VsJ2NEfB)

For further information, How To's and FAQ please check the [Wiki](https://github.com/janeczku/calibre-web/wiki)

# Contributing to Calibre-Web

Please have a look at our [Contributing Guidelines](https://github.com/janeczku/calibre-web/blob/master/CONTRIBUTING.md) 
