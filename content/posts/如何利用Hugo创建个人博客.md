---
title: "如何利用Hugo创建个人博客"
date: 2020-06-13T10:04:11+09:00
draft: false
---
## 亲手建造个人博客不是梦
Hello大家好！我是Cathy海希。
在学习编程之前，我会觉得靠自己建造一个个人博客是一件很困难的事情。但是今天我想跟告诉大家：其实很简单！快来跟我一起亲手试试吧！

## 思路整理
1. 首先，我们得需要一个网站来作为博客的载体。你会想说：“我不会建造网站！😨”不用怕，有一款免费的神器叫做[Hugo](https://gohugo.io/)可以为我们快速生成网站；
2. 光有网站了还不行，我们得把它放到互联网上，这样子人家才可以访问你的博客。
   我们可以利用Github里的[Github Pages 功能](https://pages.github.com/)来把我们的网站免费地放到互联网上。
简单来说，就是这样两个步骤，怎么样，听上去是不是没有那么困难了呢？😊那么接下来我们就一步一步来看吧！

## 通过Hugo快速生成网站🧙‍♀️
1. [Hugo Quick Start](https://gohugo.io/getting-started/quick-start/)的这篇文档把操作步骤写得很清楚，你所需要做的就是按照它的指示把命令行一行一行输入到终端里就好了。Step 2需要注意一下，我们这里自定义一下，输入`hugo new site xxx(你的Github账号名).github.io-creator ` 有两点补充一下：
* 在这里要用Github的账号名作为new site的名字，是因为之后我们需要把它和我们的Github账号连接起来。
* 好奇的话可以使用`code xxx(你的Github账号名).github.io-creator`来查看里面的内容，这就是Hugo的厉害之处，快速地为我们创建出了这么多东西。
2. 完成之后，你会得到一个public目录，顾名思义，这个目录就是我们要用于展现给大众的网站所在地啦。（public目录是位于xxx(你的Github账号名).github.io-creator目录里的）
3. 通过执行`hugo server`命令，你就可以通过访问包含在回复的内容里的[http://localhost:1313](http://localhost:1313)来预览你的网站。
不过注意，这个时候地址栏里写的是*local*哦，也就意味着我们需要将它放上互联网，让全世界的人都可以看到。
![通过Hugo快速建立的网站](https://i.loli.net/2020/06/13/UqlgzrFCGL1VdxP.png)

## 把网站搬到Github Pages上🌍
[Github Pages]（https://pages.github.com/）是Github推出的可以预览HTML页面的一项功能，所以我们的思路是：把包含网站所有文件的目录（叫public）上传到Github上，然后用Github Pages功能让互联网上的所有人都可以看到这个目录的内容（即网站）。这一步跟上一步相比会复杂一点，让我们慢慢来。
1. 我们需要把我们想要展示的`public`目录上传到Github上去，所以我们得在这个目录里建立一个git仓库。
    但是大家记不记得，在上一步[Hugo Quick Start](https://gohugo.io/getting-started/quick-start/)的Step 3为了添加主题的时候，我们已经把`public`目录所在的`xxx.github.io-creator`git init过了！所以我们需要告诉爸爸`xxx.github.io-creator`，您旗下的儿子`public`要独立了，您不要管它。如何操作呢？
    在`xxx.github.io-creator`目录里，建立一个`.gitigore`文档，里面写上`/public/`就可以了。
独立宣言发表完之后，我们就可以安心地在`public`目录下执行`git init`了。

2. 然后是`git add .`添加所有文件，`git commit -m (你想写的备注）`提交。

👆上面两步的本质就是建立好了网站所在目录的本地仓库，
👇我们还需要去Github上建立可以对应它的远程仓库。

3. 在Github上新建一个仓库，仓库名必须取名为`xxx(你的Github账号名).github.io`。
   
4. 在`public`目录里，执行
   ```git remote add origin git@github.com:xxx/xxx.github.io.git```
     添加远程主机,告诉`public`目录，“这就是你要对应的远程仓库哦！”。

5. 在`public`目录里，执行
   ```git push -u origin master```
   将`public`目录里的master分支推送到远程主机的master分支上。
   （以上两步的代码在新建仓库之后Github都会提供，复制粘贴即可）   

好，终于做完了Github的部分，接下来就要进入高潮部分Github Pages的设定了！是不是有点小兴奋呢？

6. 点击进入`xxx(你的Github账号名).github.io`仓库右上角的setting，往下滑你就会看到期待已久的GitHub Pages啦！
   ![找到GitHub Pages](https://i.loli.net/2020/06/13/nhgACBpxHPtUrEj.png)
   如果你的页面和我一样，那就不需要做什么；如果不一样，选择master分支，然后保存即可。

7. 终于，你就可以通过URL`xxx(你的Github账号名).github.io`来访问自己的博客网站啦🎉
   快快将你的网站和这篇教程分享给你的朋友们吧！

See you next time！❤️

