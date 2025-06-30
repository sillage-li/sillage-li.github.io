---
weight: 1
date: 2025-06-30T23:11:28+08:00
draft: false
title: 'Hugo Build'
---
Hugo build, hugo 的构建与自部署

## Hugo build 
## 安装

访问 https://github.com/gohugoio/hugo/releases , 直接安装满足你操作系统 (**Windows**, **Linux**, **macOS**) 的最新版本 [{{< fa-icon regular file-archive >}} Hugo (> 0.122.0)](https://gohugo.io/getting-started/installing/).
选择最新版的一个 Release 包(最好包含extended, 其支持更多功能)

以下步骤可帮助你初始化新网站. 如果你根本不了解 Hugo, 我们强烈建议你按照此 [快速入门文档](https://gohugo.io/getting-started/quick-start/) 进一步了解它.



配置环境变量
1. windows： 编辑环境变量 path -> hugo 解压后的位置


## 创建一个属于你的项目

Hugo 提供了一个 `new` 命令来帮助你创建工程
```bash
hugo new site your_website
cd your_website
```

## 安装主题

你可以访问 [Hugo](https://gohugo.io/) 官网页面中的 Themes 模块(或直接打开  [Themes](https://themes.gohugo.io/))， 选择一个喜欢的主题模板，通过 `download` 按钮链接访问仓库地址。 此处以 DoIt 为例子。(https://github.com/HEIGE-PCloud/DoIt.git)
这里有两种安装方式
### 压缩包
你可以下载主题的 [最新版本 {{< fa-icon regular file-archive >}} .zip 文件](https://github.com/HEIGE-PCloud/DoIt/releases) 并且解压放到 `themes` 子目录下.
### git 子模块(推荐)
此方式可以保证模块的更新
```bash
git clone https://github.com/HEIGE-PCloud/DoIt.git themes/DoIt
```

## 快速使用
theme.DoIt 文件下有一个 exampleSite 文件夹， 这个是此主题的一个样例。我们借助他提供的样例来快速构建可以预览的页面。
1. 复制此文件夹下的 `content` 和 `config` 包到项目的根目录下。
2. 编辑 config-> _default -> hugo.toml 文件, 修改 `themesDir="/themes"`(指定主题的文件夹， 之前是在 exampleSite 文件夹下利用相对路径定位)
3. 修改 config-> _default -> permalinks.toml 文件, 修改 `posts = ":filename"`(此操作和Hugo的版本有关， 之前的 `contentbasename` 不再支持)
4. 控制台使用命令 `hugo server -D` 本地启动项目进行预览。

## github pages 托管
