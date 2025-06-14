# 我的个人博客 (My Personal Blog)

欢迎来到我的个人博客项目仓库！

本博客基于 [Hexo](https://hexo.io/zh-cn/) 博客框架搭建，并使用了功能强大且高度可定制的 [NexT](https://theme-next.js.org/) 主题。

**线上访问地址**: [https://你的用户名.github.io](https://你的用户名.github.io)  <!-- 请将这里的链接替换成你自己的博客地址 -->

---

## 快速开始

本项目依赖于 Node.js 和 Git 环境。在开始之前，请确保你已经安装了它们。

### 1. 环境准备

如果你在一台新电脑上操作，需要先安装以下软件：

- **Node.js**: [官方网站](https://nodejs.org/zh-cn/) (请选择 LTS 版本)
- **Git**: [官方网站](https://git-scm.com/downloads)

安装完成后，打开命令行工具（如 PowerShell 或 Git Bash），执行以下命令全局安装 Hexo 命令行工具：

```bash
npm install -g hexo-cli
```

### 2. 克隆并初始化项目

将本仓库克隆到本地：

```bash
git clone https://github.com/你的用户名/你的仓库名.git  # 替换成你的仓库地址
cd 你的仓库名 # 进入项目目录
```

进入项目目录后，安装所有依赖项：

```bash
npm install
```
> **注意**: 如果 `npm install` 失败或速度过慢，可以尝试使用 `cnpm` 或 `yarn`。

### 3. 本地预览

所有准备工作就绪后，执行以下命令即可在本地启动一个实时预览服务器：

```bash
hexo server
```
或者使用简写命令：
```bash
hexo s
```

启动成功后，命令行会提示：
`Hexo is running at http://localhost:4000/ . Press Ctrl+C to stop.`

此时，在浏览器中打开 `http://localhost:4000` 即可看到你的博客。你在本地对文章或配置所做的任何修改，通常刷新浏览器就能实时看到效果。

---

## 日常使用指南

### 撰写新文章

使用以下命令来创建一篇新的文章：

```bash
hexo new "你的文章标题"
```
例如：
```bash
hexo new "Hexo 使用心得分享"
```

该命令会在 `source/_posts/` 目录下创建一个名为 `你的文章标题.md` 的 Markdown 文件。使用任何你喜欢的 Markdown 编辑器（如 VS Code, Typora）打开并编辑它即可。

文章的开头部分是 **Front-matter**，用于配置文章的元信息，非常重要：
```yaml
---
title: Hexo 使用心得分享
date: 2023-10-28 10:00:00  # 文章创建时间
tags:
  - Hexo
  - 博客
categories: 技术教程
---

这里是你的正文内容...
```

### 生成静态文件

在你准备发布网站之前，需要先将所有的 Markdown 文件和配置文件转换成纯静态的 HTML 文件。执行以下命令：

```bash
hexo generate
```
或者使用简写命令：
```bash
hexo g
```
生成的文件会存放在项目根目录下的 `public` 文件夹中。

### 部署到线上

当你在本地确认所有修改无误后，执行以下命令将网站部署到 GitHub Pages（或其他你配置的服务器）：

```bash
hexo deploy
```
或者使用简写命令：
```bash
hexo d
```
这个命令会自动将 `public` 文件夹中的内容推送到你在 `_config.yml` 文件中配置的 `deploy` 仓库地址。

### 日常更新流程（三步曲）

一个典型的日常更新流程如下：

1.  **写文章**：`hexo new "新标题"`，然后编辑 `.md` 文件。
2.  **本地预览**：`hexo s`，在浏览器中检查效果。
3.  **发布上线**：`hexo clean && hexo g && hexo d`。

> `hexo clean` 命令用于清除缓存和旧的生成文件，是一个好习惯，可以避免一些奇怪的缓存问题。

---

## 个性化配置

本项目的配置分为两部分：

1.  **站点配置**: 位于项目根目录的 `_config.yml` 文件。这里负责配置网站的标题、作者、URL、部署信息等全局设置。

2.  **主题配置**: 位于 `themes/next/_config.yml` 文件。这里负责配置主题的外观，如风格、头像、菜单、社交链接、动画效果、评论系统等。
    > **重要提示**: 强烈建议优先修改 **主题配置文件** (`themes/next/_config.yml`)，而不是站点配置文件，来调整外观和功能。

---

## 常用命令汇总

| 命令 | 完整命令 | 功能描述 |
| :--- | :--- | :--- |
| `hexo n "标题"` | `hexo new "标题"` | 新建一篇文章 |
| `hexo g` | `hexo generate` | 生成静态文件 |
| `hexo s` | `hexo server` | 启动本地预览服务器 |
| `hexo d` | `hexo deploy` | 部署网站 |
| `hexo clean` | `hexo clean` | 清除缓存和已生成的静态文件 |
| `hexo g -d` | `hexo generate --deploy` | 生成并立即部署 |
| `hexo new page "页面名"` | `hexo new page "页面名"`| 创建一个独立页面（如 "关于" 页面） |