# 📱 OpenClaw 手机相关技能合集

本仓库包含两个 OpenClaw 技能：
- **phone-charger** - 手机充电头评测技能
- **phone-review** - 手机专业评测技能

---

## 📦 技能介绍

### 1. phone-charger - 手机充电头评测

从功率、协议兼容性、体积、纹波四个维度综合评测充电头。

| 维度 | 权重 | 说明 |
|------|------|------|
| 充电功率 | 30% | 最大输出功率 (W) |
| 协议支持 | 25% | 支持的快充协议数量 |
| 体积大小 | 20% | 尺寸体积 (cm³) |
| 纹波大小 | 25% | 输出纹波 (mV)，越低越好 |

**适用场景：**
- "推荐一个充电头"
- "苹果 96W 充电头怎么样？"
- "哪个充电头性价比高？"

---

### 2. phone-review - 手机专业评测

从续航、影像、性能、屏幕、外观质感、性价比 6 个维度全面评测手机。

| 维度 | 评估内容 |
|------|----------|
| 续航 | 电池容量、充电功率、续航测试 |
| 影像 | 摄像头、传感器、变焦、夜景/视频 |
| 性能 | 处理器跑分、游戏表现 |
| 屏幕 | 分辨率、刷新率、亮度、色准 |
| 外观质感 | 材质、工艺、重量、手感 |
| 性价比 | 配置与价格对比 |

**适用场景：**
- "评测一下 iPhone 15 Pro"
- "小米 14 和 OPPO Find X7 哪个好？"
- "推荐一款拍照好的手机"

---

## 🛠️ 安装到其他 OpenClaw

### 方式一：SkillHub 安装（推荐）

```bash
# 安装 phone-charger 技能
skillhub install phone-charger

# 安装 phone-review 技能  
skillhub install phone-review
```

### 方式二：手动安装

#### Step 1: 找到技能目录

不同安装方式对应不同路径：

| 安装方式 | 技能目录路径 |
|----------|--------------|
| OpenClaw 主工作区 | `<workspace>/skills/` |
| 用户个人空间 | `~/.openclaw/workspace/skills/` |
| 插件扩展 | `<openclaw>/extensions/*/skills/` |

#### Step 2: 复制技能文件

将技能文件夹复制到目标 OpenClaw 的 skills 目录：

```bash
# 复制 phone-charger
cp -r phone-charger /path/to/your/openclaw/skills/

# 复制 phone-review
cp -r phone-review /path/to/your/openclaw/skills/
```

#### Step 3: 重启 OpenClaw

```bash
# 重启 Gateway
sh /path/to/openclaw/scripts/restart.sh

# 或者使用 openclaw 命令
openclaw gateway restart
```

---

## 📂 目录结构

```
openclaw-skills/
├── README.md                 # 本文件
├── phone-charger/            # 充电头评测技能
│   ├── SKILL.md             # 技能定义文件
│   ├── skill.json           # 技能配置
│   └── README.md            # 技能说明
└── phone-review/            # 手机评测技能
    └── SKILL.md             # 技能定义文件
```

---

## 🔧 OpenClaw 技能规范

每个技能必须包含以下文件：

| 文件 | 必填 | 说明 |
|------|------|------|
| `SKILL.md` | ✅ | 技能定义，包含名称、描述、使用说明 |
| `skill.json` | ❌ | 可选的技能配置 |

### SKILL.md 格式

```yaml
---
name: 技能名称
description: 技能简短描述
metadata: 
  # 可选的元数据
---

# 技能详细说明

## 使用方法
...

## 示例
...
```

---

## 📖 更多信息

- [OpenClaw 官方文档](https://docs.openclaw.ai)
- [SkillHub 技能商店](https://clawhub.com)
- [创建自己的技能](https://docs.openclaw.ai/skills)

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

---

**更新日期**: 2026-03-23
