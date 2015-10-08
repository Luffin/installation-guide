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
#####编辑器（个人喜好了，信安方向的话，推荐Sublime Text 3）
* 官网下载sublime text 3 OS X版
* 在[这里](http://www.xiumu.org/note/sublime-text-3.shtml)有破解、配置、安装中文包的详细方法。这里附上__License__
```	
----- BEGIN LICENSE -----
Andrew Weber
Single User License
EA7E-855605
813A03DD 5E4AD9E6 6C0EEB94 BC99798F
942194A6 02396E98 E62C9979 4BB979FE
91424C9D A45400BF F6747D88 2FB88078
90F5CC94 1CDC92DC 8457107A F151657B
1D22E383 A997F016 42397640 33F41CFC
E1D0AE85 A0BBD039 0E9C8D55 E1B89D5D
5CDB7036 E56DE1C0 EFCC0840 650CD3A6
B98FC99C 8FAC73EE D2B95564 DF450523
------ END LICENSE ------
```

* 为Sublime Text 3配置Python开发环境
	* __ctrl+`__粘贴运行下列代码安装Package Control
		
		```import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())```
	* `command + shift + p`，在里面输入`package control`，再选择`install package`，输入`SublimeCodeIntel`安装输入提示插件，很不错！
	* 和上一步一样，安装`SublimeREPL`插件，这个插件可以在Sublime里使用Python的raw_input()和input()了。安装好之后在`perferences -- key bindings user`中粘贴如下代码(其中的__f5__可以自定义):	
	
			[ {"keys":["f5"],"caption": "SublimeREPL: Python - RUN current file","command": "run_existing_window_command", "args":{"id": "repl_python_run","file": "config/Python/Main.sublime-menu"}}]

#####Binwalk:后门(固件)分析利器
* `brew install binwalk`

#####Metasploit渗透测试神器
* [点击这里](http://www.freebuf.com/articles/system/36924.html)有安装的详细说明
* 但是要特别注意的是，这篇文章时间略早，msf对应的ruby版本已经有了变化，具体可以在github的metasploit项目里查看msf最新适合的ruby版本，目前的版本是`ruby 2.1.6p336`
* __需要注意的是，老版本中的msfpaylode、msfencode现在统一到同一个命令下，叫`msfvenom`，使用`msfvenom -h`查看使用方法__

#####Nmap(扫描神器)
* `brew install nmap`安装nmap

#####Sqlmap(sql注入神器)
* `brew install sqlmap`安装


#####MAMP(Apache＋PHP＋MySQL环境)
* 安装好后，打开`.zshrc`文件，把里面的`export PATH`改为`export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Applications/MAMP/Library/bin/"`这样就可在打开MAMP之后直接在终端输入`mysql`进入mysql终端界面

#####UItraEdit(16进制编辑器)
* 在machunter中搜索即可下载到破解中文版

#####BurpSuite(抓包神器)
* [破解版下载地址](http://www.freebuf.com/tools/18483.html)
* [使用介绍](http://drops.wooyun.org/tools/1548)


#####FireFox浏览器(附带各种牛逼插件)
* AutoProxy(快速设置代理插件，可配合BurpSuite使用)
* HackBar
* FireBug
* ModifyHeaders

#####Python模块
* BeautifulSoup(HTML解析)
* pwntools(CTF快速编写exploit指定产品)
* requests(比urllib、urllib2更简单好用)

#####Wireshark(网络嗅探抓包神器)
* 自行官网下载





				
###以下顺序任意
* 词典(Mac自带的词典比较少，而且没有专门的计算机词典，需要自己下载)
	* 这边提供一个算是全的网站[http://abloz.com/huzheng/stardict-dic/zh_CN/](http://abloz.com/huzheng/stardict-dic/zh_CN/)
	* 下载`DictUnifler`软件，打开软件将下载对文件包拖入软件中转换生成词典文件。软件会将生产的词典文件自动导入到词典软件的词典目录中
	* 打开词典软件偏好设置，勾选并拖动词典以调整顺序
*	mou（markdown必备）
*	dash（api文档）
*	chrome（firefox不是调试的话就不管吧）
	*	chrome插件推荐
		*	postman
		*	editthiscookie
		*	switchyomega
		*	剩下的看自己需求
*	shadowsocksX（翻墙啊）
*	alfred2（感觉很厉害）
*	百度云盘（hehe~）
*	迅雷
*	搜狗拼音（）
