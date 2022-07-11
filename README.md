# MyBlog

## Access address of the website

> Welcome to explore！

address: [Boyu Blog](https://www.caiboyu.online/)



## Dev + Ops

### Hugo

个人博客由[Hugo](https://gohugo.io/)生成，Hugo是一个简单简洁的网站构建工具。

使用`Hugo`之前你需要有以下环境：

* Git

* Go

* node.js

#### Build website

1. 切换到你的目录下

2. 键入命令生成站点：

   ```bash
   hugo new site yourname
   ```

   查看其目录结构：

   ```xml
   +------------
   │  config.toml # 配置文件
   ├─archetypes
   │      default.md
   ├─content # 存放文章
   ├─data 
   ├─layouts
   ├─static # 静态资源：图片等
   └─themes # 存放Hugo主题
   ```

3. 添加主题：

   依据各主题自带`README.md`文件进行添加，通常包括：

   ```bash
   cd themes
   git clone XXXX
   ```

   个人博客：https://link.zhihu.com/?target=https%3A//themes.gohugo.io/hugo-theme-dream/

4. 本地运行：

   ```bash
   hugo server
   ```

5. 访问本地链接：http://localhost:1313/

### launched

* 域名购买
* 网站备案
* SSL证书申请
* Nginx部署

参考博客：https://www.vpsss.net/19231.html

  
