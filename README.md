# mini_blog

这是一个微型个人博客项目。在网上找了很多博客项目，发现要么就是很重的功能齐全的标准博客系统，要么是长时间没有维护的小型博客系统。最关键的是都不太符合我的要求。我想建立一个微型个人博客，不要太多功能，也不要太重的mysql数据库。只要支持markdown转为html格式展示在我的博客网站上，再加上时间列表，标签列表，阅读数量等。差不多就足够了。目标是足够精简。简约即是美。

# 技术栈
```markdown
python
flask
markdown
Sqlite3


```


# 使用手册
```markdown


python  app.py


```



### 技术性介绍
从markdown编辑开始，最后到博客网页上流程为：
1. 将编辑好的markdown（包括使用到的资源，如图片等）拷贝到svn目录下，提交到svn服务器。
2. 在服务器上启动定时服务crontab，每隔固定时间（例如30分钟）用bash脚本去检测一次svn是否需要更新。
3. 当请求博客时，flask服务会检测到markdown目录已经有了新的文件，生成最新的博客列表。并转化markdown为html，并保存为html文件，下次直接返回对应html。

主要在flask的基础上使用Python开发，其他还用到bash脚本去检测svn更新。主要支持显示markdown列表到网页上，支持标签列表，支持日期列表，博客转化显示等。

demo展示地址：http://www.rockgame.info
