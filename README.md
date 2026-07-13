<p align="center">
  <img src="assets/banner.jpg" alt="Kino Design System">
</p>

<h1 align="center">Kino — Web Design Framework</h1>

<p align="center">
  以天气为灵感的主题式设计框架<br>
  中文 | <a href="README_EN.md">English</a>
</p>

---

## 简介

Kino 是一套以天气现象命名的主题式设计框架，采用三层隔离架构：

- **主题层** `styles/` — CSS 变量驱动视觉风格，换主题 = 换 CSS 文件
- **组件层** `components/` — 纯展示 UI 单元，每个组件独立文件夹，自包含 HTML+CSS+JSON
- **页面层** `pages/` — 完整页面，数据与模板分离

## 当前主题

| 风格 | 版本 | 色调 |
|---|---|---|
| [Twilight（暮光）](styles/twilight/README.md) | v1.0.0 | 琥珀 `#e8922a` + 青色 `#14b8a6`，暖色深色底 |

## 目录结构

```
kino/
├── assets/                       README 图片资源
├── styles/                       主题层
│   └── twilight/tokens.css       CSS 变量（唯一真相源）
├── components/                   组件层（每个组件独立文件夹）
│   ├── button/button.html        组件预览 + 样式 + 契约
│   ├── card/
│   ├── table/
│   ├── chart/
│   ├── navigation/
│   ├── sidebar/
│   └── index.json                组件索引
├── pages/                        页面层
│   └── dashboard/
│       ├── index.html            页面模板
│       └── data/                 数据文件（JSON）
├── contracts/                    规则与元数据
│   ├── AI_RULES.md               AI 架构规则（最重要）
│   └── styles-index.json         主题注册表
└── README.md
```

## 核心约束

1. **组件绝不包含数据或业务逻辑** — 只负责"长什么样"
2. **加功能 = 新建文件夹** — 不修改任何已有文件
3. **所有样式值通过 CSS 变量消费** — 换主题只需换 CSS

## 许可

MIT
