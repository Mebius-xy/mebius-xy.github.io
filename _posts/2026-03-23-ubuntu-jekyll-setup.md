---
title: Ubuntu 搭建 Jekyll 全记录：从红叉到绿勾
date: 2026-03-23 08:00:00 +0800
categories: [技术复盘, Linux]
tags: [ubuntu, jekyll, git]
comments: true  # <--- 必须显式设置为 true，否则 Chirpy 会隐藏评论区
---

## 避坑指南
今天最深刻的教训是 **Git Token 权限**。

### 核心报错
> `refusing to allow a Personal Access Token to update workflow`

**原理分析**：
这是因为 `.github/workflows/` 属于敏感路径，普通的 `repo` 权限无法修改它，必须开启 `workflow` 作用域。

### 常用命令总结
- 启动服务：`bundle exec jekyll serve`
- 强制清理：`bundle exec jekyll clean`