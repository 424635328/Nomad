<div align="center">

#  Nomad's Blog - 源代码仓库

**✨ 在代码的世界里游牧，记录每一次探索与成长 ✨**

</div>

<p align="center">
  <!-- Vercel 部署状态 -->
  <a href="https://vercel.com/424635328s-projects/nomad" target="_blank">
    <img src="https://vercelbadge.vercel.app/api/424635328s-projects/nomad" alt="Vercel Deployment">
  </a>
  <!-- 在线访问 -->
  <a href="https://nomad-rho-nine.vercel.app/" target="_blank">
    <img src="https://img.shields.io/badge/Blog-在线访问-0098AC?style=for-the-badge&logo=vercel" alt="Blog">
  </a>
  <!-- 最后提交 -->
  <img src="https://img.shields.io/github/last-commit/424635328/Nomad?style=for-the-badge&logo=git&logoColor=white" alt="Last Commit">
</p>

## 📌 导航目录 (Table of Contents)

- [💡 项目理念 (Philosophy)](#-项目理念-philosophy)
- [🏗️ 技术架构 (Architecture)](#️-技术架构-architecture)
- [🚀 本地开发工作流 (Local Development)](#-本地开发工作流-local-development)
- [✍️ 内容创作指南 (Content Creation)](#️-内容创作指南-content-creation)
- [☁️ 部署与上线 (Deployment)](#️-部署与上线-deployment)
- [🔧 配置深度解析 (Configuration Deep Dive)](#-配置深度解析-configuration-deep-dive)
- [❓ 常见问题排查 (FAQ)](#-常见问题排查-faq)
- [🙏 致谢 (Acknowledgements)](#-致谢-acknowledgements)

## 💡 项目理念 (Philosophy)

"Nomad" (游牧者) 代表了在广袤的数字世界中不断迁徙、学习和探索的精神。本博客旨在成为我的“数字营地”，用以：

-   **记录**：沉淀技术学习中的关键知识点与实践经验。
-   **思考**：复盘项目，反思成长，将零散的想法系统化。
-   **分享**：将有价值的内容分享给社区，与同行交流互助。

---

## 🏗️ 技术架构 (Architecture)

本博客采用现代化的静态站点方案，实现了高效、安全、免费的托管。

-   **静态站点生成**: [**Hexo**](https://hexo.io/zh-cn/) - 快速、简洁且强大的博客框架。
-   **主题渲染**: [**Fluid**](https://hexo.fluid-dev.com/) - 一款如水般流畅、优雅且功能丰富的 Hexo 主题。
-   **包管理**: [**pnpm**](https://pnpm.io/) - 快速、节省磁盘空间的 Node.js 包管理器。
-   **持续集成与部署 (CI/CD)**: [**Vercel**](https://vercel.com/) - 提供全球 CDN 加速、自动化构建和免费托管。

### 分支策略 (Branching Strategy)

-   `main` 分支: **源代码分支**。所有文章的撰写、配置的修改都在此分支进行。
-   Vercel 会自动监听 `main` 分支的 `git push` 事件，并触发自动构建和部署。

---

## 🚀 本地开发工作流 (Local Development)

### 1. 环境准备 (Prerequisites)

-   **Git**: [官方下载](https://git-scm.com/downloads)
-   **Node.js**: **推荐 `v18.x` 或更高版本的 LTS**。 [官方下载](https://nodejs.org/zh-cn/)
-   **pnpm**: 通过 `npm` 全局安装: `npm install -g pnpm`

### 2. 初始化项目 (Initialization)

```bash
# 1. 克隆本仓库
git clone https://github.com/424635328/Nomad.git

# 2. 进入项目目录
cd Nomad

# 3. 安装依赖 (请务必使用 pnpm)
pnpm install

# 4. 全局安装 Hexo 命令行 (若未安装)
npm install -g hexo-cli
```
> **⚠️ 重要提示**: 本项目已锁定使用 `pnpm`。请**不要**使用 `npm` 或 `yarn` 安装依赖，以免破坏 `pnpm-lock.yaml` 文件，导致依赖不一致或部署失败。

### 3. 启动本地预览

```bash
# 启动实时预览服务器
hexo server

# 如果需要预览草稿文件夹 (_drafts) 中的文章
hexo server --draft
```
服务器启动后，访问 `http://localhost:4000` 即可预览。

---

## ✍️ 内容创作指南 (Content Creation)

### 1. 新建文章或页面

```bash
# 新建文章
hexo new "你的文章标题"

# 新建独立页面 (如 "关于" 页面)
hexo new page "about"
```

### 2. Front-matter 详解

Front-matter 是位于 Markdown 文件最顶部的 YAML 配置块，用于定义页面元数据。

```yaml
---
title: "深入理解 Vercel 自动化部署"
date: 2024-05-20 14:00:00
tags: [CI/CD, Vercel, Hexo]
categories: "DevOps"
cover: /img/covers/vercel-deploy.png # Fluid 主题特色：文章封面图
---
```
更多可配置项请参考 [Hexo Front-matter 文档](https://hexo.io/zh-cn/docs/front-matter)。

### 3. 资源管理 (图片等)

本项目已启用 `post_asset_folder: true`。这意味着：
1.  执行 `hexo new "文章标题"` 时，会自动在 `source/_posts` 下创建一个同名文件夹。
2.  将该文章所需的所有图片、附件等放入此文件夹。
3.  在 Markdown 中使用**相对路径**引用图片，例如 `![图片描述](./image.png)`。
这样做可以保证图片的管理与文章绑定，非常清晰且不易出错。

---

## ☁️ 部署与上线 (Deployment)

**本项目的部署流程已完全由 Vercel 自动化，无需手动执行 `hexo deploy`。**

### 自动化部署工作流

新的工作流极其简单：

1.  在本地完成文章撰写或配置修改。
2.  将更改提交到 Git：
    ```bash
    git add .
    git commit -m "feat: 添加新文章《关于 Vercel》"
    ```
3.  将提交推送到 GitHub 的 `main` 分支：
    ```bash
    git push origin main
    ```
4.  **完成！** Vercel 会自动检测到推送，拉取最新代码，执行构建命令（`pnpm install && hexo generate`），并将生成的内容部署到全球节点。你可以在 Vercel 的 Dashboard 中查看实时部署日志。

### 手动部署 (备用)
如果需要（例如，部署到备用服务器），依然可以执行传统的手动部署命令：`hexo clean && hexo g && hexo d`。但这已不是本项目的主要部署方式。

---

## 🔧 配置深度解析 (Configuration Deep Dive)

- **Hexo 核心配置 ([`_config.yml`](https://github.com/424635328/Nomad/blob/main/_config.yml))**:
  负责网站的底层设置，如 URL、永久链接格式、资源文件夹等。详细配置请参阅 [Hexo 配置文档](https://hexo.io/zh-cn/docs/configuration)。

- **Fluid 主题配置 ([`_config.fluid.yml`](https://github.com/424635328/Nomad/blob/main/_config.fluid.yml))**:
  **所有外观和功能的定制都应在此文件进行**。这种分离配置的方式可以让你在未来轻松升级主题内核，而不会丢失个性化设置。

  > **必读**: 在进行定制前，请务必仔细阅读 [**Fluid 官方配置指南**](https://hexo.fluid-dev.com/docs/guide/)，它详细解释了每一个配置项。

---

## ❓ 常见问题排查 (FAQ)

**Q1: Vercel 部署失败了，怎么办？**
> **A:** 1. **查看日志**: 在 Vercel 的部署详情页，仔细阅读 "Build Logs"。绝大多数错误信息（如依赖安装失败、命令执行错误）都会在这里显示。 2. **本地模拟**: 在本地执行 Vercel 的构建命令 `pnpm install && hexo generate`，看是否能成功。如果本地也失败，说明是项目本身的问题。 3. **检查 Node.js 版本**: Vercel 默认使用较新的 Node.js 版本，可以在 Vercel 项目的 "Settings" -> "General" -> "Node.js Version" 中指定版本，使其与你的本地环境一致。

**Q2: 如何在 Vercel 上绑定自定义域名？**
> **A:** 在 Vercel 项目的 "Settings" -> "Domains" 页面，输入你的域名并添加。Vercel 会提示你需要在你的域名注册商处添加 CNAME 或 A 记录。配置完成后，Vercel 会自动为你签发和续期免费的 SSL 证书。

**Q3: 如何升级 Fluid 主题？**
> **A:** 访问 [Fluid 的 GitHub Releases 页面](https://github.com/fluid-dev/hexo-theme-fluid/releases)，下载最新版本的 `source code (zip)`，解压后替换掉你项目中的 `themes/fluid` 文件夹。由于你的所有配置都在外部的 `_config.fluid.yml` 文件中，升级过程通常是无缝的。

---

## 🙏 致谢 (Acknowledgements)

本博客的诞生离不开以下优秀的开源项目与服务：

-   [**Hexo**](https://hexo.io/) - 强大的静态站点生成器。
-   [**Fluid**](https://github.com/fluid-dev/hexo-theme-fluid) - 优雅、美观的主题。
-   [**Vercel**](https://vercel.com/) - 提供了无与伦比的开发与部署体验。
-   [**GitHub**](https://github.com/) - 提供了代码托管和社区的基石。

<div align="center">

---
*感谢你的阅读，让我们一起在编码的世界里不断探索。*

</div>
