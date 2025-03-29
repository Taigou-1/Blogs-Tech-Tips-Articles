# Git和GitHub CLI使用笔记

## 1.使用Github CLI在远程仓库中的release中上传文件

使用GitHub时，在release中上传文件经常遇到上传不成功的的问题，通过以下方法可以解决

需要准备GitHub CLI和Git

按win+R，在出现的窗口中输入cmd，按enter键，电脑会打开cmd窗口

输入gh auth login，（在GitHub CLI上登录你的Github账号）

![](https://github.com/Taigou-1/Blogs-Tech-Tips-Articles/blob/main/assets/1.png)

窗口中会出现一些问题，建议依次选择【GitHub.com】,【HTTPS】，【Yes】，【Login with a web browser】，按照这些操作，就完成登录了。

然后，输入这行代码，可以把文件上传到（确保已经在网页端创建了release）

```
gh release upload TAG名称 文件路径 --repo username/repositorie-name
```

将你的【TAG名称】【文件路径】【username】【repositorie-name】替换到对应的位置，例如：

```
gh release upload 1.4.2 C:\Users\Think\Desktop\release1.4.2.zip --repo Taigou-1/Browser-Page-Text-Editor
```

当窗口中出现“Successfully uploaded 1 asset to”，就说明你的文件成功上传到了release中。
