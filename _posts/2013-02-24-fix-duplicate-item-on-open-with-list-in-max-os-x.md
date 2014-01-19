title: 修复 Mac OS X 打开方式 重复项
date: 2013-02-24 18:26:14
tags: Mac
categories: tech
---

{% code lang:bash %}
/System/Library/Frameworks/CoreServices.framework/Frameworks/LaunchServices.framework/Support/lsregister -kill -r -domain local -domain system -domain user
{% endcode %}

1. 在控制台输入上面代码，回车运行。
2. 重启Finder(在Dock上的Finder 图标上按住control + option + 点击)
3. Check it now
