# 个人技术博客

基于 Jekyll 和 GitHub Pages 构建的个人博客网站，使用 [Beautiful Jekyll](https://github.com/daattali/beautiful-jekyll) 主题。

## 功能特性

- ✅ 使用 Markdown 编写文章
- ✅ 自动构建和部署到 GitHub Pages
- ✅ 响应式设计，支持移动端
- ✅ RSS 订阅支持
- ✅ 代码高亮
- ✅ 美观现代的 Beautiful Jekyll 主题
- ✅ 社交链接支持
- ✅ 分类和标签功能

## 如何写新文章

1. 在 `_posts` 目录下创建新的 Markdown 文件
2. 文件名格式：`YYYY-MM-DD-文章标题.md`（使用英文或拼音，用连字符分隔）
3. 在文件开头添加 Front Matter（元数据）：

```yaml
---
layout: post
title:  "文章标题"
date:   2024-01-20 14:30:00 +0800
categories: 分类名称
---
```

4. 使用 Markdown 语法编写文章内容
5. 提交并推送到 GitHub，GitHub Pages 会自动构建和发布

## 本地开发

### 安装依赖

```bash
# 安装 Ruby（如果还没有）
# macOS: brew install ruby
# 或使用 rbenv/rvm

# 安装 Bundler
gem install bundler

# 安装项目依赖
bundle install
```

### 运行本地服务器

```bash
bundle exec jekyll serve
```

然后在浏览器中访问 `http://localhost:4000`

## 配置

编辑 `_config.yml` 文件来配置网站信息：

- `title`: 网站标题
- `description`: 网站描述
- `author`: 作者名称
- `email`: 邮箱地址
- `url`: 网站 URL
- `github_username`: GitHub 用户名

## 目录结构

```
.
├── _config.yml          # Jekyll 配置文件
├── _posts/              # 博客文章目录
│   └── YYYY-MM-DD-title.md
├── about.md             # 关于页面
├── index.html           # 首页
├── Gemfile              # Ruby 依赖
└── README.md            # 说明文档
```

## 参考资源

- [Jekyll 官方文档](https://jekyllrb.com/)
- [GitHub Pages 文档](https://docs.github.com/pages)
- [Markdown 语法指南](https://www.markdownguide.org/)
