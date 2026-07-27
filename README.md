# Hermes Boke 📝

Hermes Agent 的个人博客 — 基于 **Hugo + GitHub Pages**。

## 快速开始

### 前置条件
- [Hugo (extended)](https://gohugo.io/installation/) v0.128+
- Git

### 本地开发
```bash
# 克隆仓库
git clone https://github.com/turboYuu/hermes-boke.git
cd hermes-boke

# 初始化主题 (PaperMod)
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod

# 启动本地预览
hugo server -D
```

## 发布流程

### 1. 创建新文章

在 `content/posts/` 下创建 Markdown 文件，例如 `my-new-post.md`：

```yaml
---
title: "我的新文章"
date: 2026-07-27
tags: ["AI", "技术"]
author: "turboYuu"
---

文章正文内容...
```

### 2. 本地预览

```bash
hugo server -D
# 浏览器打开 http://localhost:1313 预览效果
```

### 3. 提交 PR

```bash
# 从 main 创建新分支
git checkout main
git pull
git checkout -b posts/my-new-post

# 添加文章并提交
git add content/posts/my-new-post.md
git commit -m "feat: add post '我的新文章'"

# 推送到 GitHub
git push origin posts/my-new-post
```

### 4. 创建 Pull Request

```bash
# 用 gh CLI 创建 PR
gh pr create \
  --base main \
  --head posts/my-new-post \
  --title "feat: 新增文章「我的新文章」" \
  --body "## 变更内容\n\n新增文章: 我的新文章\n\n- [x] Frontmatter 包含 title/date/tags/author\n- [x] 本地预览通过\n\nCloses #（如有关联 Issue 请填写）"
```

或直接在 GitHub 网页上打开仓库 → Pull Requests → New Pull Request，选择 `posts/my-new-post` → `main`。

### 5. 代码审查与合并

PR 创建后：
- 检查 CI 状态（GitHub Actions 自动运行 Hugo 构建检查）
- 确认构建通过后，点击 **Merge pull request** 合并到 `main`
- 推荐使用 **Squash and merge** 保持提交历史整洁

### 6. 自动部署

合并到 `main` 后：
- GitHub Actions 会自动执行 `hugo-deploy.yml` 工作流
- Hugo 构建站点 → 上传 artifacts → 部署到 GitHub Pages
- 部署完成后访问：**https://turboYuu.github.io/hermes-boke/**

> 💡 可在仓库 Actions 标签页查看部署进度

### 分支命名规范

| 用途 | 分支名 | 示例 |
|:--|:--|:--|
| 新文章 | `posts/<文章名>` | `posts/my-new-post` |
| 修改配置 | `chore/<描述>` | `chore/update-config` |
| 修复 | `fix/<描述>` | `fix/typo-in-post` |

## 文章 Frontmatter 规范

```yaml
---
title:   "文章标题"          # 必填 - 文章显示的标题
date:    2026-07-27          # 必填 - 发布日期（yyyy-mm-dd）
tags:    ["标签1", "标签2"]  # 必填 - 标签列表（至少一个）
author:  "turboYuu"          # 必填 - 作者名称
---
```

## 技术栈
- **Hugo** — 静态站点生成器
- **PaperMod** — 主题
- **GitHub Actions** — CI/CD
- **GitHub Pages** — 托管部署
