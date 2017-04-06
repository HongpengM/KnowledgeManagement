Sublime 调配python IDE指南



下载地址

https://www.sublimetext.com/3

sublime比较轻量

然后如果配置pythonIDE需要做的是这样

首先安装package control 就是一个插件管理器

https://packagecontrol.io/installation

按Ctrl +｀在控制台里输入网页里面那一堆

然后等一小会就好

以后可以按住Ｃｔｒｌ　＋　ｓｈｉｆｔ　＋　Ｐ调出ｐａｃｋａｇｅ　ｃｏｎｔｒｏｌ

其中比较主要的就是ｉｎｓｔａｌｌ　ｐａｃｋａｇｅ功能



然后需要调缩进，在Preference--Setting里面的User setting加上下面代码

{

	
	"ignored_packages":
	[
		"Vintage"
	],

"tab_size": 4,
	"translate_tabs_to_spaces": true
}

然后python响应式命令行需要安装SublimeREPL插件

Ctrl +Shift + P 打开package install然后输入intall package

然后会出现各种包 输入sublimeREPL会默认出来，按回车会自动安装

设置编译运行的快捷键， Preference--Keybindings里面的user的那个文件里面输入

然后keys里面就是绑定快捷键

[

    { "keys": ["f5"], "command": "run_existing_window_command", "args":
        {
            "id": "repl_python_run",
            "file": "config/Python/Main.sublime-menu"
        }
    }
]

代码风格自动检查的插件Anaconda

安装方式同上

配置方式Preference--Package Settings--Settings - User

里面添加



{

    //忽略各种空格不对, 超过80字, import的函数没有使用的提醒,
    "pep8_ignore": ["E501", "W292", "E303", "W391", "E225", "E302", "W293", "E402"],
    "pyflakes_explicit_ignore":
    [
        "UnusedImport"
    ],
    //保存文件后自动pep8格式化
    "auto_formatting": true,
    //库函zhuti数的提示
    "enable_signatures_tooltip": true,
    "merge_signatures_and_doc":true,
    /*
        Set is a false to disable Anaconda Linting totally
    */
    "anaconda_linting": false,
}

主题的风格可以在网上找喜欢的下载

我装的是material theme

就是Ctrl + shift + P  --> install package --> material theme --> RETURN

然后在Preference -- color theme 里面选了一个主题



然后一般常用的快捷键

Ctrl + B build and run大概是这个意思，可以对python脚本直接这样运行但是无法命令行输入，所以推荐sublimeREPL方式，

Shift + Alt + 1/2/3 。。 界面分栏

剩下的要是用的话，你可以慢慢探索，查找替换也还算方便～
满足编码转换的需求
Shift + P  install package安装 ConvertToUTF8
最近刚刚配好这个环境就写了下

