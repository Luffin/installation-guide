###mac应用安装指南（信安方向）
===
#####优先级降序排列
*	xcode（自带环境）
*	homebrew（快速环境配置）
	*	homebrew安装:
	
			ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
			
	*	终端中输入 `brew install **`
		*	一般需要安装 git python node ...
		*	`brew update` 升级brew
		*	`brew upgrade` 升级插件
*	iterm2（代替terminal终端）
	*	替换成zsh，超级方便（oh_my_zsh,github）
	*	zsh配置主题（视需求) __推荐使用agnoster__(如图)点击[这里](http://www.leelour.com/?p=2423)查看安装方法
	![agnoster](https://cloud.githubusercontent.com/assets/2618447/6316862/70f58fb6-ba03-11e4-82c9-c083bf9a6574.png)
*	machunter（可以安装各种盗版软件）
	*	adobe系列（看需求）
	*	navicat（数据库）	
	*	transmit（ftp文件管理）
	*	mamp（本地服务器搭建）
	*	istat menus（好用的硬件监控）
	*	Parallels desktop（虚拟机）
	*	个人需求了~
*	编辑器（个人喜好了，信安方向的话，Python或者PHP用`sublime text 3`很不错，推荐！）
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
		* __ctrl+`__安装Package Control
		
				import urllib.request,os; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); open(os.path.join(ipp, pf), 'wb').write(urllib.request.urlopen( 'http://sublime.wbond.net/' + pf.replace(' ','%20')).read())

	
#####以下顺序任意
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
