---
weight: 1
date: 2025-06-30T23:11:28+08:00
draft: false
title: 'Hugo Build'

authors: ["sillageli"]
description: "Hugo 的构建于自托管"
featuredImage: "hugo-logo-wide.webp"

tags: ["installation", "configuration"]
categories: ["documentation"]
series: ["getting-start"]
---

## Hugo build 
## 安装

访问 https://github.com/gohugoio/hugo/releases , 直接安装满足你操作系统 (**Windows**, **Linux**, **macOS**) 的最新版本 [{{< fa-icon regular file-archive >}} Hugo (> 0.122.0)](https://gohugo.io/getting-started/installing/).
选择最新版的一个 Release 包(最好包含extended, 其支持更多功能)

以下步骤可帮助你初始化新网站. 如果你根本不了解 Hugo, 我们强烈建议你按照此 [快速入门文档](https://gohugo.io/getting-started/quick-start/) 进一步了解它.



配置环境变量
1. windows： 编辑环境变量 path -> hugo 解压后的位置
2. macos: 建议通过 brew 安装


## 创建一个属于你的项目

Hugo 提供了一个 `new` 命令来帮助你创建工程
```bash
hugo new site your_website
cd your_website
```

## 安装主题

你可以访问 [Hugo](https://gohugo.io/) 官网页面中的 Themes 模块(或直接打开  [Themes](https://themes.gohugo.io/))， 选择一个喜欢的主题模板，通过 `download` 按钮链接访问仓库地址。
此处以 DoIt 为例子。(https://github.com/HEIGE-PCloud/DoIt.git)
这里有两种安装方式
### 压缩包
你可以下载主题的 [最新版本 {{< fa-icon regular file-archive >}} .zip 文件](https://github.com/HEIGE-PCloud/DoIt/releases) 并且解压放到 `themes` 子目录下.
或者利用 git 把此主题克隆的 `theme` 目录: 
~~~bash
git clone https://github.com/HEIGE-PCloud/DoIt.git themes/DoIt
~~~
### git 子模块(推荐)
此方式可以保证模块的更新
```bash
git init 
git submodule add https://github.com/HEIGE-PCloud/DoIt.git themes/DoIt
```

## 快速使用
theme.DoIt 文件下有一个 exampleSite 文件夹， 这个是此主题的一个样例。我们借助他提供的样例来快速构建可以预览的页面。
1. 复制此文件夹下的 `content` 和 `config` 包到项目的根目录下。
2. 编辑 config-> _default -> hugo.toml 文件, 修改 `themesDir="/themes"`(指定主题的文件夹， 之前是在 exampleSite 文件夹下利用相对路径定位)
4. 控制台使用命令 `hugo server -D` 本地启动项目进行预览。

## github pages 托管

[//]: # (在 github 仓库点击 Settings， 选择 pages ![操作图]&#40;settings-pages-actions.jpg "pages-actions"&#41;)
[//]: # ({{< image src="settings-pages-actions.webp" caption="操作" width="2450" height="1562" >}})
在 github 仓库点击 Settings, 选择 pages
{{< image src="settings-pages-actions.webp" caption="基本配置下的预览" width="2450" height="1562" >}}

点击 `browse all workflows`,进入后搜索 hugo, configure 进入编辑后修改hugo版本与当前版本相同即可保存即可。**仓库尽量选择同名的仓库， 
如：你的 github 叫 tom, 则创建一个 tom.github.io 的仓库来使用**。 <br/>
检查刚才配置的 workflows yaml, 默认应该监控的 master 分支， 尝试推送到远端后检查 actions 中是否构建成功.  成功后可访问 tom.github.io 来访问页面。