Mac下使用sublime text3配置Javascript开发环境
---




### 使用Node.js配置build system

```javascript
位置: Tools -> Build System -> New Build System
保存为 node.sublime-build,内容为:

{
    "cmd": ["/usr/local/bin/node","$file","$file_base_name"],
    "working_dir":"${project_path:${folder}}",
    "selector":"*.js"
}

```

### 安装插件

1.SublimeCodeIntel

https://github.com/SublimeCodeIntel/SublimeCodeIntel

sublime默认的代码提示只能提示系统函数，用户自己创建的函数、类不能提示。 如果想要提示自己建立的函数,或者其他函数库等。 可以安装sublimecodeintel插件

可选配置：
当有附加库时可以选择在用户主目录(`~/.codeintel/config`)或者应用根目录下(`project_root/.codeintel/config`)配置例如：

```javascript
{
    "PHP": {
        "php": '/usr/bin/php',
        "phpExtraPaths": [],
        "phpConfigFile": 'php.ini'
    },
    "JavaScript": {
        "javascriptExtraPaths": []
    },
    "Perl": {
        "perl": "/usr/bin/perl",
        "perlExtraPaths": []
    },
    "Ruby": {
        "ruby": "/usr/bin/ruby",
        "rubyExtraPaths": []
    },
    "Python": {
        "python": '/usr/bin/python',
        "pythonExtraPaths": []
    },
    "Python3": {
        "python": '/usr/bin/python3',
        "pythonExtraPaths": []
    }
}
```

2.AngularJS

---
待更新...