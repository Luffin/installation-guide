##mac应用安装指南（信安方向）
===
###优先级降序排列
#####xcode（自带环境,安装后自动集成git，可直接使用）
#####homebrew（快速环境配置）
*	homebrew安装:
	
		ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
			
*	终端中输入 `brew install **`
	*	一般需要安装 git python node ...
	*	`brew update` 升级brew
	*	`brew upgrade` 升级插件
	
#####iterm2（代替terminal终端）
*	替换成zsh，超级方便（oh_my_zsh,github）
*	zsh配置主题（视需求) __推荐使用agnoster__(如图)点击[这里](http://www.leelour.com/?p=2423)查看安装方法
	![agnoster](https://cloud.githubusercontent.com/assets/2618447/6316862/70f58fb6-ba03-11e4-82c9-c083bf9a6574.png)
*	目前个人比较喜欢`Monokai Soda`这个配色方案
	
#####macports(类似homebrew的包管理工具，可以便捷安装python里的PIL、OpenCv库)
* `brew install Caskroom/cask/macports`安装
* 将macports的路径添加到`.zshrc`里的`export PATH`中
	
#####machunter（可以安装各种盗版软件）
*	adobe系列（看需求）
	* **在Safari下有个`ClickToPlugin`的插件，可以强制转会flash视频成html5，这样看视频就不会像flash那样出现发热严重和掉电快的情况。推荐安装！**
*	navicat（数据库）	
*	transmit（ftp文件管理）
*	mamp（本地服务器搭建）
*	istat menus（好用的硬件监控）
*	Parallels desktop（虚拟机）
* 个人需求了~

===
###信安学习相关工具
####编辑器（个人喜好了，信安方向的话，推荐Sublime Text 3）
* 官网下载sublime text 3 OS X版
* 在[这里](http://www.xiumu.org/note/sublime-text-3.shtml)有破解、配置、安装中文包的详细方法。这里附上__License__

		—– BEGIN LICENSE —–
		Nicolas Hennion
		Single User License
		EA7E-866075
		8A01AA83 1D668D24 4484AEBC 3B04512C
		827B0DE5 69E9B07A A39ACCC0 F95F5410
		729D5639 4C37CECB B2522FB3 8D37FDC1
		72899363 BBA441AC A5F47F08 6CD3B3FE
		CEFB3783 B2E1BA96 71AAF7B4 AFB61B1D
		0CC513E7 52FF2333 9F726D2C CDE53B4A
		810C0D4F E1F419A3 CDA0832B 8440565A
		35BF00F6 4CA9F869 ED10E245 469C233E
		—— END LICENSE ——

* 为Sublime Text 3配置Python开发环境
	* __ctrl+`__粘贴运行下列代码安装Package Control
		
			import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
			
	* `command + shift + p`，在里面输入`package control`，再选择`install package`，输入`SublimeCodeIntel`安装输入提示插件，很不错！
	* 和上一步一样，安装`SublimeREPL`插件，这个插件可以在Sublime里使用Python的raw_input()和input()，也可以在Sublime中使用命令行Python。安装好之后在`perferences -- key bindings user`中粘贴如下代码(其中的__f5__可以自定义):	
	
			[ {"keys":["f5"],"caption": "SublimeREPL: Python - RUN current file","command": "run_existing_window_command", "args":{"id": "repl_python_run","file": "config/Python/Main.sublime-menu"}}]
	* `Anaconda`插件，代码补全、文档提示等很棒的Python插件
	* `Jedi`另一款Python插件
	* `Bracket Highlighter`插件
	* `GitGutter`插件，类似diff的比较插件
	* 一个很棒的Sublime主题[Material Theme](https://github.com/equinusocio/material-theme)，效果是这样的![Material Theme](https://camo.githubusercontent.com/1ff3f31c6a43cdf5f02e2d54a5afee6802abff23/687474703a2f2f657175696e75736f63696f2e6769746875622e696f2f6d6174657269616c2d7468656d652f6173736574732f6d756c74692e6a7067)

####Binwalk:后门(固件)分析利器
* `brew install binwalk`

####Metasploit渗透测试神器
* [点击这里](http://www.freebuf.com/articles/system/36924.html)有安装的详细说明
* 但是要特别注意的是，这篇文章时间略早，msf对应的ruby版本已经有了变化，具体可以在github的metasploit项目里查看msf最新适合的ruby版本，目前的版本是`ruby 2.1.6p336`
* __需要注意的是，老版本中的msfpaylode、msfencode现在统一到同一个命令下，叫`msfvenom`，使用`msfvenom -h`查看使用方法__

####Nmap(扫描神器)
* `brew install nmap`安装nmap

####Sqlmap(sql注入神器)
* `brew install sqlmap`安装(但是用brew安装的版本太老了)建议在brew装好sqlmap之后，再去Github上知道sqlmap的项目，把源码包下载到电脑上。到`/usr/local/Cellar/sqlmap/0.9_1`目录下，把下载的源码包名改为`libexec`替换掉原有的包。这样就能直接在终端使用`sqlmap`命令使用最新版的sqlmap了


####MAMP(Apache＋PHP＋MySQL环境)
* 安装好后，打开`.zshrc`文件，把里面的`export PATH`改为`export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Applications/MAMP/Library/bin/"`这样就可在打开MAMP之后直接在终端输入`mysql`进入mysql终端界面

####UItraEdit(16进制编辑器)
* 在machunter中搜索即可下载到破解中文版

#####BurpSuite(抓包神器)
* [破解版下载地址](http://www.freebuf.com/tools/18483.html)
* [使用介绍](http://drops.wooyun.org/tools/1548)
* [抓https包的配置，要下载burp的证书](http://blog.csdn.net/zyw_anquan/article/details/47904495)


####FireFox浏览器(附带各种牛逼插件)
* AutoProxy(快速设置代理插件，可配合BurpSuite使用)
* HackBar
* FireBug
* ModifyHeaders

####Chrome
*	Chrome插件推荐
	*	postman
	*	EditThisCookie(修改cookie)
	*	SwitchySharp(很方便的代理切换工具)
	*	Octotree(看github时的神器，在浏览器左侧生成类似编辑器的侧边栏，可以显示整个项目树，方便总览项目)
	*	OneTab(有时看到一些网站不错，但是又以下没时间看，就可以把这个网站存放在OneTab中方便以后查看)
	*	哔哩哔哩助手\_(:з」∠)\_
	*	Momentum(好看的Chrome标签页，姚总推荐)
	*	Avatars for Github(在github动态处显示出不同人的头像，看起来更方便)
	*   Power Zoom(鼠标悬停放大图片，看妹子头像\_(:з」∠)\_)
	
####Python模块
* BeautifulSoup(HTML解析)
* pwntools(CTF快速编写exploit指定产品)
* requests(比urllib、urllib2更简单好用)

####Wireshark(网络嗅探抓包神器)
* 自行官网下载

####Hashcat(各种密码破解)
* `brew install Caskroom/cask/hashcat`安装

####Hydra(暴力破解神器)
* 去Github下载[源码](https://github.com/vanhauser-thc/thc-hydra)
* 在下好的源码文件夹内依次运行以下命令

		./configure
		make
		make install
				
###以下顺序任意
* Aria2（下载神器！下载百度网盘等不会被限速）
	* 安装`brew install aria2`
	* 之后在[这里](https://github.com/yangshun1029/aria2gui)下到中文GUI版本
	* 然后在[这里](https://github.com/acgotaku/BaiduExporter/releases)下到百度网盘Chrome插件，可以在百度网盘里我的设备盘多出一个导出下载按钮，导入Aria2来下载
	* 在[这里](https://chrome.google.com/webstore/detail/yaaw-for-chrome/dennnbdlpgjgbcjfgaohdahloollfgoc)下到Chrome插件版的Aria2：`YAAW`，在Chrome浏览器中管理下载任务。__注：该插件为英文版，并且需要翻墙到谷歌商店下载__
* 词典(Mac自带的词典比较少，而且没有专门的计算机词典，需要自己下载)
	* 这边提供一个算是全的网站[http://abloz.com/huzheng/stardict-dic/zh_CN/](http://abloz.com/huzheng/stardict-dic/zh_CN/)
	* 下载`DictUnifler`软件，打开软件将下载对文件包拖入软件中转换生成词典文件。软件会将生产的词典文件自动导入到词典软件的词典目录中
	* 打开词典软件偏好设置，勾选并拖动词典以调整顺序	
*	mou（markdown必备）
*	keka目前见到的最简洁功能最全的加解压软件
*	dash（api文档）
*	shadowsocksX（翻墙啊）
*	alfred2（感觉很厉害）
*	百度云盘（hehe~）
*	迅雷*	
*	搜狗拼音
