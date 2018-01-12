mac应用安装指南(信安方向)
===
### 优先级降序排列

#### xcode(自带环境,安装后自动集成git，可直接使用)

#### homebrew(快速环境配置)
*	homebrew安装:
	
		ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
			
*	终端中输入 `brew install **`
	*	一般需要安装 git python node ...
	*	`brew update` 升级brew
	*	`brew upgrade` 升级插件
	
#### iTerm2(代替terminal终端)
*	替换成zsh，超级方便(oh_my_zsh,github)
*	zsh配置主题(视需求) __推荐使用agnoster__(如图)点击[这里](http://www.leelour.com/?p=2423)查看安装方法
	![agnoster](https://cloud.githubusercontent.com/assets/2618447/6316862/70f58fb6-ba03-11e4-82c9-c083bf9a6574.png)
*	目前个人比较喜欢`Monokai Soda`这个配色方案
*   在iTerm2[官网](http://www.iterm2.com/documentation-images.html)有一个`imgcat`插件，可以直接在命令行中查看图片，非常方便，效果类似这样![imgcat](http://www.iterm2.com/images/inline_image_sparky_demo.png)只需要在[这里](https://raw.github.com/gnachman/iTerm2/master/tests/imgcat)下载imgcat的源码，放入到`/usr/local/bin`之类的目录中，加上执行权限`chmod +x imgcat`，就可以在命令行中当做命令来调用了
	
#### alfred2(效率神器)
*   Hide Desktop(显示或隐藏桌面文件)
*   New File(在Finder中创建文件)
*   Show Desktop(收起所有软件显示桌面)
*   TerminalFinder(根据当前Finder目录打开Terminal并进入目录，或在Terminal打开对于Finder目录)
*   Layout(修改当前窗口界面布局)
*   关于Feature中的Terminal/Shell里调用iTerm代码可见[这里](https://github.com/stuartcryan/custom-iterm-applescripts-for-alfred/)

信安学习相关工具
===
#### 编辑器(个人喜好了，信安方向的话，推荐Sublime Text 3)
* 官网下载sublime text 3 OS X版
* 在[这里](http://www.xiumu.org/note/sublime-text-3.shtml)有破解、配置、安装中文包的详细方法。这里附上**License(2017.12.26)**

		—– BEGIN LICENSE —–  
		TwitterInc  
		200 User License  
		EA7E-890007  
		1D77F72E 390CDD93 4DCBA022 FAF60790  
		61AA12C0 A37081C5 D0316412 4584D136  
		94D7F7D4 95BC8C1C 527DA828 560BB037  
		D1EDDD8C AE7B379F 50C9D69D B35179EF  
		2FE898C4 8E4277A8 555CE714 E1FB0E43  
		D5D52613 C3D12E98 BC49967F 7652EED2  
		9D2D2E61 67610860 6D338B72 5CF95C69  
		E36B85CC 84991F19 7575D828 470A92AB  
		—— END LICENSE ——  

* 为Sublime Text 3配置Python开发环境
	* **ctrl+`**粘贴运行下列代码安装Package Control
		
			import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())
			
	* `command + shift + p`，在里面输入`package control`，再选择`install package`，输入`SublimeCodeIntel`安装输入提示插件，很不错！
	* 和上一步一样，安装`SublimeREPL`插件，这个插件可以在Sublime里使用Python的raw_input()和input()，也可以在Sublime中使用命令行Python。安装好之后在`perferences -- key bindings user`中粘贴如下代码(其中的__f5__可以自定义):	
	
			[ {"keys":["f5"],"caption": "SublimeREPL: Python - RUN current file","command": "run_existing_window_command", "args":{"id": "repl_python_run","file": "config/Python/Main.sublime-menu"}}]
	* `Anaconda`插件，代码补全、文档提示等很棒的Python插件
	* `Jedi`另一款Python插件
	* `Bracket Highlighter`插件
	* `GitGutter`插件，类似diff的比较插件
	* 一个很棒的Sublime主题[Material Theme](https://github.com/equinusocio/material-theme)，效果是这样的![Material Theme](https://camo.githubusercontent.com/972bd5d93779fdaf95e02cf0326b429be93adcba/687474703a2f2f692e696d6775722e636f6d2f395079784a4d4e2e676966)

#### Binwalk:后门(固件)分析利器
* `brew install binwalk`

#### Metasploit渗透测试神器
* [点击这里](http://www.freebuf.com/articles/system/36924.html)有安装的详细说明
* 但是要特别注意的是，这篇文章时间略早，msf对应的ruby版本已经有了变化，具体可以在github的metasploit项目里查看msf最新适合的ruby版本
* __需要注意的是，老版本中的msfpaylode、msfencode现在统一到同一个命令下，叫`msfvenom`，使用`msfvenom -h`查看使用方法__

#### Nmap(扫描神器)
* `brew install nmap`安装nmap

#### Sqlmap(sql注入神器)
* `brew install sqlmap`安装(但是用brew安装的版本太老了)建议在brew装好sqlmap之后，再去Github上知道sqlmap的项目，把源码包下载到电脑上。到`/usr/local/Cellar/sqlmap/0.9_1`目录下，把下载的源码包名改为`libexec`替换掉原有的包。这样就能直接在终端使用`sqlmap`命令使用最新版的sqlmap了


#### MAMP(Apache＋PHP＋MySQL环境)
* 安装好后，打开`.zshrc`文件，把里面的`export PATH`改为`export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Applications/MAMP/Library/bin/"`这样就可在打开MAMP之后直接在终端输入`mysql`进入mysql终端界面

#### 010Edit(16进制编辑器)
* 很好用，但是目前没找到破解版

#### BurpSuite(抓包神器)
* [破解版下载地址](https://github.com/x-Ai/BurpUnlimitedre)
* [使用介绍](http://drops.wooyun.org/tools/1548)
* [抓https包的配置，要下载burp的证书](http://blog.csdn.net/zyw_anquan/article/details/47904495)

#### Chrome
*	Chrome插件推荐
	*	postman
	*	EditThisCookie(修改cookie)
	*	Proxy SwitchyOmega(很方便的代理切换工具)
	*	Octotree(看github时的神器，在浏览器左侧生成类似编辑器的侧边栏，可以显示整个项目树，方便总览项目)
	*	OneTab(有时看到一些网站不错，但是又以下没时间看，就可以把这个网站存放在OneTab中方便以后查看)
	*	哔哩哔哩助手\_(:з」∠)\_
	*	Momentum(好看的Chrome标签页，姚总推荐)
	*	Avatars for Github(在github动态处显示出不同人的头像，看起来更方便)
	*   Power Zoom(鼠标悬停放大图片，看妹子头像\_(:з」∠)\_)
	*   Gliffy Diagrams画各种图
	*   pakku：哔哩哔哩弹幕过滤器
	*   

#### Wireshark(网络嗅探抓包神器)
* 自行官网下载

#### Hashcat(各种密码破解)
* `brew install Caskroom/cask/hashcat`安装

#### Hydra(暴力破解神器)
* 去Github下载[源码](https://github.com/vanhauser-thc/thc-hydra)
* 在下好的源码文件夹内依次运行以下命令

		./configure
		make
		make install
		
#### ssh-copy-id
Mac下没有`ssh-copy-id`，所以需要安装一个，会比`scp`方便
* 运行命令`brew install ssh-copy-id`使用`brew`来安装

#### dirsearch

目录扫描工具

#### jq

json命令行解析工具

#### thefuck

[thefuck](https://github.com/nvbn/thefuck)修正你在命令行输入的前一个命令
![image_here](https://raw.githubusercontent.com/nvbn/thefuck/master/example.gif) 

#### docker

搭环境神器
				
其他
===
#### Aria2(下载神器！下载百度网盘等不会被限速)

* 安装`brew install aria2`
* 之后在[这里](https://github.com/yangshun1029/aria2gui)下到中文GUI版本
* 然后在[这里](https://github.com/acgotaku/BaiduExporter/releases)下到百度网盘Chrome插件，可以在百度网盘里我的设备盘多出一个导出下载按钮，导入Aria2来下载
* 在[这里](https://chrome.google.com/webstore/detail/yaaw-for-chrome/dennnbdlpgjgbcjfgaohdahloollfgoc)下到Chrome插件版的Aria2：`YAAW`，在Chrome浏览器中管理下载任务。__注：该插件为英文版，并且需要翻墙到谷歌商店下载__

#### 词典(Mac自带的词典比较少，而且没有专门的计算机词典，需要自己下载)

* 这边提供一个算是全的网站[http://abloz.com/huzheng/stardict-dic/zh_CN/](http://abloz.com/huzheng/stardict-dic/zh_CN/)
* 下载`DictUnifler`软件，打开软件将下载对文件包拖入软件中转换生成词典文件。软件会将生产的词典文件自动导入到词典软件的词典目录中
* 打开词典软件偏好设置，勾选并拖动词典以调整顺序	

#### MacDown(markdown必备)

#### keka目前见到的最简洁功能最全的解压软件

#### dash(api文档)

#### shadowsocksX(翻墙啊)

#### 百度云盘(hehe~)

#### 搜狗拼音
