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

## 2.git基础操作

### 检验能否链接:
```
curl -I http://github.com
```

### 将仓库克隆到本地:
```
git clone <repo>
```
例如:
```
git clone https://github.com/Taigou-1/Neoforge-Mod-Development-Tutorial.git
```

### 创建仓库
创建新的仓库，将当前的目录转换成一个 Git 仓库
```
git init
```
关联到远程仓库
```
git remote add origin <url>
```
创建并切换到新分支
```
git checkout -b main
```
使用-u，设置上游分支，以后可以直接使用"git push"和"git pull"
```
git push -u origin main
```

### 改动
添加计划改动（添加到缓存区）
```
git add <文件/目录>
```
所有改动
```
git add .
```
提交改动
```
git commit -m "提交信息"
```

### 推送改动
将改动推送到远程仓库
```
git push origin main
```

### 拉取远程更新
```
git pull origin main
```

### 撤销提交
```
git revert <commit>
```
放弃当前修改
```
git reset --hard HEAD              # 丢弃所有未提交的修改（包括暂存区）
git clean -df                      # 删除所有未跟踪的文件和目录（可选）
```

### Vim 编辑器操作

按 i 进入编辑模式（如果需要修改）。

修改完成后，按 Esc 退出编辑模式。

输入 :wq 保存并退出。

### 登录github
```
git config --global user.name "账号用户名"
git config --global user.email "邮箱"
```
如果仅对一个仓库进行登录，则去掉"--global"
