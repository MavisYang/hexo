---
title: hexo搭建自己的博客
date: 2020-01-08 14:37:27
tags: MavisY
---

>Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 Markdown（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

## mac下搭建hexo+github博客

>在安装环境都已经配置完成的前提下`git`，`node.js`

### 安装hexo

- 终端执行如下命令
```
sudo npm install -g hexo
```
- 初始化，终端cd到一个指定的目录（我在~/Documents/目录下）执行如下命令
```
hexo init <folder>
```
- 终端cd到<folder>目录下，安装npm
```
cd <folder>
npm install

```
- 开启hexo服务,就可以在本地（本地预览地址`http://localhost:4000 `）预览博客主页了
```
hexo s  # 或者hexo server
```

### Github Pages设置

1. 在gitHub中创建一个项目，并且将本地安装的项目上传到gitHub中
```
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/MavisYang/hexo-blog.git
git push -u origin master
```
2. 在setting中开启GitHub Pages
- 选中master,显示`Your site is published at https://mavisyang.github.io/`成功（如图所示）
![GitHub Pages前](https://user-gold-cdn.xitu.io/2020/1/8/16f83e9862251654?w=768&h=437&f=png&s=47897)

![GitHub Pages后](https://user-gold-cdn.xitu.io/2020/1/8/16f83e9e5d7e71ff?w=742&h=378&f=png&s=39591)

### 关联已有的github
- 打开hexo创建文件夹下的_config.yml配置文件
```
eploy:
  type: git
  repository: https://github.com/MavisYang/mavisyang.github.io.git
  branch: master
```
- 在hexo文件夹目录下执行（生成）
```
hexo g # 或者hexo generate
```
- 如果报错，则执行
```
npm install hexo --save
```
- 再执行命令（部署到git上）
```
hexo d
```
- 如果报错，则执行
```
npm install hexo-deployer-git --save
```
- 然后再执行hexo g和hexo d

### 添加博客
```
hexo new 'post'  # 写博客
hexo clean       # 清除缓存文件
hexo g           # 生成新的文件
hexo d           # 同步部署到github端
```
![hexo new](https://user-gold-cdn.xitu.io/2020/1/8/16f840c5b078db12?w=246&h=81&f=png&s=5709)

### 完成

[博客地址](https://mavisyang.github.io/archives/)
[hello-world](https://mavisyang.github.io/2020/01/08/hello-world/)

### 命令
- hexo g -w
- hexo list route
- hexo list post
- npm install hexo -g #安装Hexo
- npm update hexo -g #升级
- hexo init #初始化博客
- 命令简写
- hexo n "我的博客" == hexo new "我的博客" #新建文章
- hexo g == hexo generate #生成
- hexo s == hexo server #启动服务预览
- hexo d == hexo deploy #部署

- hexo server #Hexo会监视文件变动并自动更新，无须重启服务器
- hexo server -s #静态模式
- hexo server -p 5000 #更改端口
- hexo server -i 192.168.1.1 #自定义 IP
- hexo clean #清除缓存，若是网页正常情况下可以忽略这条命令

### 参考
- [mac os下搭建hexo+github博客](https://www.jianshu.com/p/49c8168c7418)
- [Hexo + Github Pages搭建个人独立博客](https://linghucong.js.org/2016/04/15/2016-04-15-hexo-github-pages-blog/)