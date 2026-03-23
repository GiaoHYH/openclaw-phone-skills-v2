---
name: github-mirror
description: GitHub 镜像加速下载工具，自动将 GitHub URL 转换为加速链接，支持多种镜像站
metadata: {"emoji":"🚀","category":"工具","加速":{"支持":["ghproxy","mirror.ghproxy","gh.api"],"自动选择":"按速度最优"}}
---

# GitHub 镜像加速技能

当需要从 GitHub 下载文件、克隆仓库时，自动使用镜像加速。

---

## 🎯 使用场景

- 下载 GitHub 仓库的 release 文件
- 克隆 GitHub 仓库
- 下载 GitHub Actions 产物
- 访问 raw.githubusercontent.com

---

## 🚀 支持的镜像站

| 镜像站 | 地址 | 特点 |
|--------|------|------|
| ghproxy | `https://ghproxy.com/` | 稳定，推荐 |
| mirror.ghproxy | `https://mirror.ghproxy.com/` | 备选 |
| gh.api | `https://gh.api.99988866.xyz/` | 备选 |

---

## 📝 使用方法

### 自动转换

当我帮你下载 GitHub 文件时，会自动使用镜像加速：

```
# 原地址
https://github.com/user/repo/archive/refs/heads/main.tar.gz

# 自动转换为
https://ghproxy.com/https://github.com/user/repo/archive/refs/heads/main.tar.gz
```

### 手动使用

```bash
# 使用 ghproxy 加速
curl -L https://ghproxy.com/https://github.com/user/repo/archive/main.tar.gz -o repo.tar.gz

# 克隆仓库
git clone https://ghproxy.com/https://github.com/user/repo.git
```

---

## ⚡ 加速规则

### 自动识别

- `github.com` → 添加 `ghproxy.com/` 前缀
- `raw.githubusercontent.com` → 添加镜像前缀
- `gist.githubusercontent.com` → 添加镜像前缀

### fallback 机制

如果第一个镜像失败，自动尝试下一个镜像

---

## 📦 示例

### 下载 Release

```
原: https://github.com/vercel/next.js/releases/download/v14.0.0/next.js.tar.gz
加: https://ghproxy.com/https://github.com/vercel/next.js/releases/download/v14.0.0/next.js.tar.gz
```

### 克隆仓库

```
原: https://github.com/openclaw/openclaw.git
加: https://ghproxy.com/https://github.com/openclaw/openclaw.git
```

---

## ⚠️ 注意事项

1. 镜像站为第三方服务，不保证 100% 可用
2. 大文件下载建议直接使用代理
3. 私有仓库无法通过镜像加速

---

## 🔧 备选方案

如果镜像不可用，可使用：
- **JSDelivr CDN**: `https://cdn.jsdelivr.net/gh/user/repo@tag/file`
- **Statically**: `https://cdn.statically.io/gh/user/repo/tag/file`
- **GitClone**: `https://gitclone.com/github.com/user/repo`
