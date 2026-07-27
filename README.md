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

### 发布流程
1. 在 `content/posts/` 下创建 Markdown 文件
2. Frontmatter: `title`, `date`, `tags`, `author`
3. 提交 PR 到 `main` 分支
4. 合并后 GitHub Actions 自动部署

## 技术栈
- **Hugo** — 静态站点生成器
- **PaperMod** — 主题
- **GitHub Pages** — 托管部署
