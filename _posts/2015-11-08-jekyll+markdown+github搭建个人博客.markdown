---
layout: post
title:  "如何快速搭建博客？"
categories: jekyll update
---
jekyll是一个静态站点生成器，可以根据Markdown文件自动生成静态的html文件。且github pages 支持托管jekyll。

因此我只要在本地编写符合Jekyll规范的Markdown文件，上传到github上，github pages就会自动生成并托管整个网站。

这样做带来的好处是：

1.	专注。只需要关注Markdown内容的编写。无需考虑标签和样式，也不会干扰git的log。
2.  历史版本。通过git历史可以看到自己思维的变迁。
3.  免费，不限流量。
4.  简单。你只要用自己喜欢的编辑器写文章就可以了，其他事情一概不用操心，都由github处理。


> 机器环境:Win7 64位

-   **安装rubyinstaller.**
    1.   到[http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/ "http://rubyinstaller.org/downloads/")下载ruby安装文件，这里下载**rubyinstaller-2.2.3-x64.exe**，按照提示安装，勾选Add Ruby executables to your PATH.
   
         ![](http://i.imgur.com/ll47i5c.png)
  
    2.  Win7 64位默认安装位置：C:\Ruby22-x64.
    3.  验证ruby是否安装成功：cmd中ruby -v显示ruby版本号说明ruby安装成功.
    
-   **安装rubygems.**
   
    1.  官网下载安装包[https://rubygems.org/pages/download](https://rubygems.org/pages/download "https://rubygems.org/pages/download")
    2.  解压rubygems-2.4.8.zip到指定目录，为了方便管理解压后放到C:\Ruby22-x64\目录下.
    3.  cmd进入rubygems-2.4.8目录下(快捷键：打开C:\Ruby22-x64\rubygems-2.4.8目录，shift+鼠标右键，点击"在此处打开命令行窗口"),运行setup.rb.cmd 中 gem -v 显示版本号则说明正常.
-   **安装DevKit-mingw64**
     1.  下载相应版本[http://rubyinstaller.org/downloads/](http://rubyinstaller.org/downloads/ "http://rubyinstaller.org/downloads/"),在C:\Ruby22-x64\目录下新建DevKit文件夹，运行**DevKit-mingw64-64-4.7.2-20130224-1432-sfx.exe**后会提示解压目录，选择C:\Ruby22-x64\DevKit.
     2.  在C:\Ruby22-x64\DevKit中打开cmd，运行`ruby dk.rb init`，会提示配置config.yml.
     
         ![](http://i.imgur.com/wTvR64K.png)

     3.  打开C:\Ruby22-x64\DevKit目录下的config.yml，将ruby根目录加入到配置文件中，这里是C:/Ruby22-x64.如果有了就不需要再加.注意格式.
         
         ![](http://i.imgur.com/oH8HCQI.png)
         
            
     4.  执行ruby dk.rb install.
     
-    **替换rubyGem库地址（相当重要，因为国内访问外网有线路问题，不仅更新速度慢，而且还会导致更新失败）**
      1.  gem sources --remove https://rubygems.org/
      2.  gem sources -a http://ruby.taobao.org/
      3.  gem sources -l验证一下.
      ![](http://i.imgur.com/FIuowBr.png)
      

-    **安装rails**
     1.  cmd运行gem install rails.
     2.  cmd运行rails -v显示rails版本号说明安装成功.
-    **安装jekyll**
     1.  cmd运行gem install jekyll
     2.  cmd运行jekyll -v验证，显示版本号说明安装成功.


------------------------
环境配置完整之后，下面进入正题，如何新建博客:

-    运行命令:jekyll new  文件夹名，比如jekyll new blog，会在当前目录生成blog文件夹.
        
       ![](http://i.imgur.com/XsZ79C2.png)

-    在生成的blog文件夹根目录下运行命令:jekyll serve --watch
-    浏览器中打开localhost:4000，命令运行过程中没有错误提示，浏览器中显示默认页面说明安装成功.

       ![](http://i.imgur.com/9ljL0i6.png)

-    使用markdown发布博客
     1.  markdown是什么？ 参考淘宝UED关于markdown的介绍[http://ued.taobao.org/blog/2012/07/getting-started-with-markdown/](http://ued.taobao.org/blog/2012/07/getting-started-with-markdown/ "http://ued.taobao.org/blog/2012/07/getting-started-with-markdown/").  锤子手机发布会上罗永浩介绍了锤子科技出品的app**锤子便签**支持markdown功能，下载地址：[http://bbs.smartisan.com/forum-92-1.html](http://bbs.smartisan.com/forum-92-1.html "锤子便签app")，非常好用，建议下载体验一番.
         
     2.  将markdown、html格式的文件以"YY-MM-DD-finename.filetype"命名放到_post文件夹下：如2015-09-10-firstpost.markdown.
       
-    发布到github
     1.   首先注册一个[github](https://github.com/)账号.
     2.   新建repository,以username.github.io的形式命名.
     3.   git提交本地代码到github.
     4.   git提交命令
           -  git init
           -  git add .
           -  git commit -m "update"
           -   git remote add origin https://github.com/cseryp/cseryp.github.io.git
           -   git push -u origin master
-   参考文章
    1.  [每个人都应该有一个Jekyll博客](http://www.cellier.me/2015/01/04/jekyll%E6%90%AD%E5%BB%BA%E5%8D%9A%E5%AE%A2%E6%95%99%E7%A8%8B/)
    2.  [git教程](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)
     
          

     
     

     


