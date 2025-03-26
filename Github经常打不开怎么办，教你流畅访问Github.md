# Github经常打不开怎么办，教你流畅访问Github

如果你经常遇到Github网站打不开、不稳定，或是不流畅的问题，这篇文章大概率能帮到你。
网上有很多种关于这个问题的解决方法，我选出了其中最简单且有效的一种，并做改进。Github打不开的主要问题是[DNS污染](https://baike.baidu.com/item/DNS%E6%B1%A1%E6%9F%93?fromModule=lemma_search-box)，通过修改host将可以解决这个问题。

## 解决方法

在桌面上新建文本文档并打开，输入以下命令：
```bat
@echo off
start "" "C:\Program Files\Google\Chrome\Application\chrome.exe" ^
--host-rules="MAP github.com octocaptcha.com, MAP github.githubassets.com yelp.com, MAP *.githubusercontent.com githubusercontent.com" ^
--host-resolver-rules="MAP octocaptcha.com 20.27.177.113, MAP yelp.com 199.232.240.116, MAP githubusercontent.com 199.232.176.133" ^
"https://github.com/"
exit
```
保存，然后重命名为Github-host.bat，注意不要保留.txt后缀
需要注意的是文件路径与C:\Program Files\Google\Chrome\Application\chrome.exe是否一致，如果不一致，则需要修改为正确的路径。

你的电脑中需要有谷歌浏览器，你也可以选择其他浏览器，例如Microsoft Edge，需要把命令中的
```bat
C:\Program Files\Google\Chrome\Application\chrome.exe
```
改为
```bat
C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe
```
