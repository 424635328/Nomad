<div align="center">

#  Nomad's Blog - 源代码仓库

**✨ 欢迎来到我的数字花园，一个记录、思考与分享的技术空间 ✨**

</div>

<p align="center">
  <!-- 在线访问 -->
  <a href="https://424635328.github.io/Nomad/" target="_blank">
    <img src="https://img.shields.io/badge/Blog-在线访问-brightgreen?style=for-the-badge&logo=micro.blog" alt="Blog">
  </a>
  <!-- 构建状态 -->
  <a href="https://github.com/424635328/Nomad/actions/workflows/pages.yml" target="_blank">
    <img src="https://img.shields.io/github/actions/workflow/status/424635328/Nomad/pages.yml?branch=main&style=for-the-badge&logo=githubactions&logoColor=white" alt="Build Status">
  </a>
  <!-- 依赖状态 -->
  <a href="https://github.com/424635328/Nomad/blob/main/package.json" target="_blank">
    <img src="https://img.shields.io/github/package-json/v/424635328/Nomad?style=for-the-badge&logo=npm" alt="Version">
  </a>
  <!-- 最后提交 -->
  <img src="https://img.shields.io/github/last-commit/424635328/Nomad?style=for-the-badge&logo=git&logoColor=white" alt="Last Commit">
</p>

## 📖 项目概述 (Overview)

本仓库是我的个人博客网站的**源代码**。它使用 [Hexo](https://hexo.io/zh-cn/) 进行静态站点生成，并采用优雅的 [NexT](https://theme-next.js.org/) 主题进行渲染。所有文章均以 Markdown 格式书写，通过 GitHub Actions 自动部署到 [GitHub Pages](https://pages.github.com/)。

- **博客主题**：技术分享、学习笔记、项目复盘、生活感悟。
- **技术栈**：`Hexo` | `NexT Theme` | `Node.js` | `pnpm` | `Markdown` | `GitHub Pages`

---

## 🚀 环境搭建与本地运行 (Setup & Local Development)

在开始之前，请确保你的开发环境满足以下要求。

### 1. 必备环境 (Prerequisites)

- **Git**: 版本控制系统。 [官方下载](https://git-scm.com/downloads)
- **Node.js**: JavaScript 运行环境。**推荐 `v18.x` 或更高版本的 LTS**。 [官方下载](https://nodejs.org/zh-cn/)
- **pnpm**: 高效的包管理器。通过 `npm` 全局安装：

  ```bash
  npm install -g pnpm
  ```

### 2. 初始化项目 (Initialization)

```bash
# 1. 克隆本仓库到本地
git clone https://github.com/424635328/Nomad.git

# 2. 进入项目目录
cd Nomad

# 3. 使用 pnpm 安装所有项目依赖
pnpm install

# 4. 全局安装 Hexo 命令行工具 (如果尚未安装)
npm install -g hexo-cli
```

> **⚠️ 重要提示**: 本项目已锁定使用 `pnpm` 作为唯一的包管理器。请**不要**使用 `npm install` 或 `yarn install`，以免造成依赖冲突和不可预知的错误。

### 3. 本地预览 (Run Locally)

执行以下命令，即可在本地启动一个实时预览服务器，默认端口为 `4000`。

```bash
hexo server
# 简写: hexo s
```

服务器启动后，在浏览器中访问 `http://localhost:4000`。你对文章或配置的任何修改，都将实时反映在浏览器中（部分配置修改可能需要重启服务）。

---

## ✍️ 日常工作流 (Daily Workflow)

### 1. 新建内容

- **新建文章**:

  ```bash
  hexo new "你的文章标题"
  ```

  这将在 `source/_posts/` 目录下生成对应的 `.md` 文件。

- **新建独立页面** (例如 "友链" 页面):

  ```bash

  h  exo new page "links"

  ```
  
  这将在 `source/` 目录下创建一个 `links` 文件夹，内含 `index.md`。

### 2. 撰写与编辑

使用你喜欢的 Markdown 编辑器（如 VS Code, Typora）打开 `.md` 文件进行创作。请特别注意文件头部的 **Front-matter** 区域，它控制着文章的各种元数据。

**一个标准的 Front-matter 示例:**

```yaml
---
title: "深入理解 Hexo 工作流" # 文章标题
date: 2024-05-20 14:00:00      # 发表日期 (用于排序)
updated: 2024-05-21 10:30:00   # 更新日期 (可选)
tags:                          # 标签 (可有多个)
  - Hexo
  - 博客
  - 前端
categories: "技术教程"          # 分类 (通常只有一个)
# cover: /images/post-cover.jpg # 文章封面 (可选, 需主题支持)
# toc: false                     # 是否显示目录 (可选, 覆盖全局设置)
---
```

### 3. 部署上线 (Deployment)

本项目采用**手动触发部署**的模式。

```bash
# 完整的三步流程，确保万无一失

# 步骤 1: 清理旧缓存和已生成的 public 目录
hexo clean

# 步骤 2: 生成最新的静态文件到 public 目录
hexo generate

# 步骤 3: 将 public 目录的内容推送到 GitHub Pages
hexo deploy
```

为图方便，后两步可合并为 `hexo g -d`。

---

## 🔧 配置与定制 (Configuration & Customization)

### 1. 文件结构概览

```bash
.
├── .github/              # GitHub Actions 工作流配置
├── .vscode/              # VS Code 编辑器建议配置
├── scaffolds/            # 文章和页面的模板文件
├── source/               # 博客源文件 (文章、页面、图片等)
│   ├── _posts/           # 所有文章都在这里
│   └── ...
├── themes/               # 主题文件夹
│   └── next/             # NexT 主题源码
├── .gitignore            # Git 忽略文件配置
├── _config.yml           # ❗ Hexo 核心配置文件
├── _config.next.yml      # ❗ NexT 主题配置文件 (推荐)
├── package.json          # 项目依赖信息
└── pnpm-lock.yaml        # pnpm 锁文件，确保依赖版本一致
```

### 2. 核心配置文件

- **站点配置 (`_config.yml`)**:
  - **Site**: `title`, `subtitle`, `author`, `language`, `url` 等基本信息。
  - **Deployment**: `deploy` 部分配置了部署的目标仓库和分支，**请勿轻易修改**。

- **主题配置 (`_config.next.yml`)**:
  - 这是从 `themes/next/_config.yml` **分离**出来的用户配置文件，**所有主题相关的修改都应在此进行**。
  - **Scheme**: 切换 NexT 的不同外观风格 (Muse/Mist/Pisces/Gemini)。
  - **Menu**: 配置导航栏菜单项。
  - **Avatar/Social**: 设置头像和社交媒体链接。
  - **Features**: 开/关各种功能，如代码复制、阅读进度条、评论系统等。

> **最佳实践**: 始终在 `_config.next.yml` 中修改主题配置，而不是直接动 `themes/next/` 目录下的文件。这样可以让你在未来平滑升级主题，而不会丢失自己的定制。

---

## ❓ 常见问题排查 (FAQ)

**Q1: `hexo d` 部署失败，提示权限问题或认证失败。**
> **A:** 确保你的电脑已经配置好了对 GitHub 的 SSH 密钥认证。如果你使用的是 HTTPS 协议部署，可能需要配置 Personal Access Token (PAT) 或使用 Git Credential Manager。检查 `_config.yml` 中的 `repo` 地址是否正确。

**Q2: 修改了配置，但本地预览没效果。**
> **A:** 首先尝试 `Ctrl+C` 停止 `hexo server` 服务后重新启动。对于某些深层配置的修改，可能需要执行 `hexo clean` 清理缓存后再启动服务。

**Q3: 图片显示不出来怎么办？**
> **A:** 推荐使用 Hexo 的 [资源文件夹](https://hexo.io/zh-cn/docs/asset-folders) 功能。确保 `_config.yml` 中的 `post_asset_folder` 设置为 `true`。这样 `hexo new "文章名"` 时会自动创建同名文件夹，把图片放进去，然后在 Markdown 中使用相对路径 `![alt](./图片名.png)` 即可。

**Q4: 如何升级 NexT 主题？**
> **A:** 由于我们没有使用 Git Submodule，升级主题最简单的方式是去 [NexT 官网](https://theme-next.js.org/) 查看最新版本的发布说明，然后下载新的主题包，替换掉 `themes/next` 文件夹。因为你的配置都在 `_config.next.yml` 里，所以基本不会受影响。

---

## 🤝 贡献与支持 (Contributing & Support)

虽然这是一个个人博客项目，但如果你发现了任何拼写错误、配置问题或有更好的实践建议，非常欢迎通过以下方式参与：

- **提交 Issue**: 描述你发现的问题或建议。
- **发起 Pull Request**: 如果你能直接修复问题，那就更棒了！

<div align="center">

---
*感谢你的阅读，让我们一起在编码的世界里不断探索。*

</div>