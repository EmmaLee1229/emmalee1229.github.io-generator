---
title: "如何用Hugo搭建博客"
date: 2020-04-24T00:15:02+08:00
draft: false
---

### 本文仅以 Mac 为例

## 1. 需在 bash 里安装 Hugo

```
brew install hugo
```

安装完成时运行`hugo version` 进行检查是否安装成功,若显示版本号则为成功

## 2.创建一个新的网站

```
hugo new site quickstart
```

运行上述命令将在`quickstart`文件中创建一个新的 hugo 网站

## 3.为博客添加一个主题

```
cd quickstart
git init
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
```

默认的主题是`ananke`，若想更换主题可以在[主题](<(https://themes.gohugo.io/)>)中搜索，然后在把主题加入配置中，命令如下：

```
echo 'theme = "ananke"' >> config.toml
```

## 4. 接下来可以开始你的第一篇博客啦

```
hugo new posts/my-first-post.md
```

在`my-first-post`可以添加任何你想写的名字。（备注：若想建立其他的博客的时候请在博客生成器的文件夹重新运行上面的命令）

然后你就可以看到一篇如下图所示的文章界面
![](/public/images/5.png)
`title`是你博客的名字你可以自己更改，`draft`表示你的这篇文章是否要上传，若为`true`则表示它是一篇草稿，无法浏览页面，若为`false`则表示已上传可以浏览页面。

## 5. 现在运行 Hugo server

```
hugo server -D
```

你会在 bash 看到
![](/public/images/6.jpg)

其中红框内的是你的本地的博客地址，请单击[博客](http://localhost:1313/)在浏览器上进行查看，你可以通过查看此页面观察你博客的更改状态，备注：不要关掉`hugo server`！！！！

## 6. 更新你的博客主页

在`vscode`里打开`config.toml`

![](/public/images/7.jpg)
你可以把语言改成`zh-Hans`,备注：若后期部署至`Github`后，若出现打开链接，然后显示如下图时

![](/public/images/8.jpg)

请把`baseURL`里面的`example.org`换成你部署的`Github`的域名，一般以`.io`结尾

## 7. 接下来就是建立静态网址啦

1. 不要关掉你现在运行的终端，新建一个终端，并在里面运行`Hugo`
2. 这时候，它会在目录里面创建一个`public`文件
3. 此时你需要在文件中创建一个`.gitignore`文件
4. 然后在里面写入`/public/`,然后进入`public`文件
5. 把`public`文件上传到你新建的`Github`仓库里
6. 然后到`setting`里面找到`Github pages`里面有一个网址就是你部署在 GitHub 上的博客啦。
