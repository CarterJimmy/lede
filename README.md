# LEDE系统的编译
## 该系统由[Lean](https://github.com/coolsnowwolf/lede)基于OpenWrt项目进行编写，在此感谢大神的耕耘。此仓库为本人的二次修改/编译版本。

- 注意：
1. 不要用 root 用户 git 和编译
2. 国内用户请使用全局科学上网
3. 默认登陆IP 192.168.1.1, 密码 password

编译命令如下:

1. 首先装好 Ubuntu Server 64bit，

2. 命令行输入 `sudo apt-get update` ，
   然后输入
`sudo apt-get -y install build-essential asciidoc binutils bzip2 gawk gettext git libncurses5-dev libz-dev patch unzip zlib1g-dev lib32gcc1 libc6-dev-i386 subversion flex uglifyjs git-core gcc-multilib p7zip p7zip-full msmtp libssl-dev texinfo libglib2.0-dev xmlto qemu-utils upx libelf-dev autoconf automake libtool autopoint`

3. `git clone https://github.com/CarterJimmy/lede/` 命令下载好源代码，然后 `cd lede` 进入目录

4. `./scripts/feeds update -a`
   `./scripts/feeds install -a`
   `make menuconfig`

5. 最后选好你要的路由，输入 `make -j1 V=s` （-j1 后面是线程数。第一次编译推荐用单线程，国内请尽量全局科学上网）即可开始编译你要的固件了。

> 特别提示：
1. 源代码中绝不含任何后门和可以监控或者劫持你的 HTTPS 的闭源软件，SSL 安全是互联网最后的壁垒。安全干净才是固件应该做到的。
2. 如果你自认为 Koolshare 论坛或者其固件的脑残粉，本人不欢迎你使用本源代码。所以如果你是，那么使用过程中遇到任何问题本人概不回应。
