title: Chrome Developer Tools Tricks
date: 2013-02-20 17:09:53
tags: [chrome, console]
categories: tech
---

1. Beautify JavaScript

    很多网站的JavaScript都是压缩过的，难以阅读，以前都是用
    [Online JavaScript Beautifier](http://jsbeautifier.org/)
    来解压缩。
    
    其实Chrome内置了这个功能。
    
    打开控制台`<F12>`，在Scripts这个选项下，左下角有个`{}`的图标（Pretty print），点一下就
    可以解压缩。

1. 快捷键
    * 在Chrome Developer tools打开(快捷键`<F12>`)的情况下，按`ctrl+shift+F`,即可查找JavaScript源代码
    * 在Scripts选项下，按`ctrl+shift+o`，查找函数名
    * 在Scripts选项下，按`ctrl+o`， 查找脚本文件
    * 忘了快捷键怎么办？想看其他快捷键肿么半？
        * 在console界面中按`?`号查看帮助

1. XHR

    在console`右键`，选中`Log XMLHttpRequests`，当有ajax时，会在console中
    打印日志。
    
    第二个选项是`Preseve Log Upon Navigation`， 切换页面，原先的日志不会
    消失。

2. console.time('name') / console.timeEnd('name')    

    `console.time()` 用来计算代码的运行时间，在console中打印出来。用
    `console.timeEnd()`来标示结束的位置。
    
    参数为这段计时器的名称

3. console.dir() / dir

    返回DOM对象所有属性值
    
4. inspect(DOM)

    自动inspect到当前dom元素。

5. $0 $1 $2

    用Developer Tools选择过页面元素后，在console中输入`$0`，即会打印当前
    选中元素的DOM信息。类似`getElementById`
    
    `$1` 可以打印前一次选中的DOM
    
    `$N` 可以打印前N次选中的DOM

6. $$() 

    类似`querySeletorAll()`
    
    > `$$('#id .class p')` 取出id是“id”中的子元素class是“class”的子元
    素tag是“p”标签的所有节点

7. monitorEvents() / unmonitorEvents()

    用来观察事件
    
    > `monitorEvents($$('body'))` 打印body元素上所有的发生的事件
    
    还可以添加第二参数，用来限制观察那种类型的事件，官方api现在貌似支
    持下面几个参数：
    
    > `mouse key touch control`
    
    > `monitorEvents($$('body'), 'key')` 打印body元素上有关键盘所有的事件

    > **mouse:**  “mousedown”, “mouseup”, “click”, “dblclick”,
      “mousemove”, “mouseover”, “mouseout”, “mousewheel” 

    > **key:** “keydown”, “keyup”, “keypress”, “textInput”

    > **touch:**  “touchstart”, “touchmove”, “touchend”,
      “touchcancel”

    > **control:**  “resize”, “scroll”, “zoom”, “focus”, “blur”,
      “select”, “change”, “submit”, “reset”

    > **no arguments:** all of the above + “load”, “unload”, “abort”, “error”, “select”, “change”, “submit”, “reset”, “focus”, “blur”, “resize”, “scroll”, “search”, “devicemotion”, “deviceorientation”

8. keys(obj) 

    打印对象所有属性

9. values(obj) 

    返回对象所有属性的值

10. copy(str)

    将str复制到系统剪切板
    
11. **更多**[console api] [1]

    Chrome和Firebug类似


12. **更多**[command line api] [2]


## Opera

1. jQuery    

    console输入
    
    `// jquery`
    
    自动载入jquery库

## Firefox

1. iframe

    `cd()`
    
    切换上下文

## Links

[Become a JavaScript Console Power-User](https://www.youtube.com/watch?feature=player_embedded&v=4mf_yNLlgic#!)

[Chrome Develoepr Tools Doc](https://developers.google.com/chrome-developer-tools/docs/overview)

[chrome developer tool 调试技巧](http://ued.taobao.com/blog/2012/06/03/debug-with-chrome-dev-tool/)

[1]: http://getfirebug.com/wiki/index.php/Console_API#console.trace.28.29 "Console APi"

[2]: http://getfirebug.com/wiki/index.php/Command_Line_API      "Command Line Api"