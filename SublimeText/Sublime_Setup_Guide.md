# ST3 调配python IDE指南


ST3下载地址1
https://www.sublimetext.com/3

**Package Control** Setup
首先安装package control 就是一个插件管理器
https://packagecontrol.io/installation

## Python IDE Setup And Markdown Setting


install Package
REPL: sublimeREPL
Code Style: Anaconda
Theme: Material Theme
Markdown Preview: MarkdownPreview
Markdown Edit: MarkdownEditing
(
安装时请关闭MD文件，否则会保持，或关闭MD文件并重启ST3 
)
Encoding: ConvertToUTF8

### 缩进调整：  --Preference--Settings--User:

```
{
    "ignored_packages":
    [
        "Vintage"
    ],
    "tab_size": 4,
    "translate_tabs_to_spaces": true
}
```
### 快捷键设置 --Preference--Key Bindings

```
[
    // F5设置为编译执行python
    { 
        "keys": ["f5"],
         "command": "run_existing_window_command",
         "args":{
            "id": "repl_python_run",
            "file": "config/Python/Main.sublime-menu"
        }
    },
    // Alt+M设置为预览md
    {
        "keys":["alt+m"],
        "command":"markdown_preview",
        "args":{
            "target": "browser",
             "parser":"markdown"
        }
    }
]
```
### Anconda 插件设置  --Preference--Package Settings--Anaconda--Settigs--User
```
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
    //   Set is a false to disable Anaconda Linting totally
    "anaconda_linting": false,
    // Set default python interpreter path
    "python_interpreter": "/Users/k/anaconda3/python3",
}
```

### Markdown Shortcut
```
Alt + M: Show Preview in Browser
Ctrl + cmd + K: insert links
Shift + cmd + K: insert photos
```
