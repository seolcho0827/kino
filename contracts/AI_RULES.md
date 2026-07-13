# Kino — AI 架构规则

Kino 是一个三层隔离的网页设计框架。

## 三层架构

| 层 | 目录 | 职责 | 能做什么 | 不能做什么 |
|---|---|---|---|---|
| **主题层** | `styles/{name}/` | 提供 CSS 变量（颜色、字体、间距、阴影、圆角） | 定义视觉风格 | 不包含组件逻辑、不包含页面布局 |
| **组件层** | `components/{name}/` | 纯展示 UI 单元 | 通过 HTML+CSS 渲染外观 | 不包含数据、不包含交互逻辑、不包含 API/路由/状态 |
| **页面层** | `pages/{name}/` | 组装组件成完整页面 | 从 `data/*.json` 读取数据，拼接组件 | 不修改组件文件 |

## 核心规则

1. **组件自包含**：每个组件是一个独立文件夹 `components/{name}/`，内含 `{name}.html`（预览）、`{name}.css`（样式）、`{name}.json`（组件契约）。打开 HTML 即可独立预览，不依赖其他组件。

2. **数据与模板分离**：页面数据放在 `pages/{name}/data/*.json`，页面模板在 `pages/{name}/index.html` 中引用组件并注入数据。

3. **加功能 = 新建文件夹**：加组件 → `components/new-name/`，加页面 → `pages/new-name/`，加主题 → `styles/new-name/tokens.css`。绝不修改已有文件。

4. **主题切换**：组件通过 `var(--xxx)` 消费所有样式值。换主题只需在 HTML 中更换 `<link rel="stylesheet" href="styles/{name}/tokens.css">`。

## 目录结构速览

```
kino/
├── styles/                   主题层
│   └── twilight/tokens.css   当前唯一主题
├── components/               组件层（6 个）
│   ├── button/button.html + button.css + button.json
│   ├── card/
│   ├── table/
│   ├── chart/
│   ├── navigation/
│   └── sidebar/
├── pages/                    页面层
│   └── dashboard/
│       ├── index.html        页面模板
│       ├── plan.json         页面组合计划
│       └── data/*.json       独立数据文件
└── contracts/                规则与元数据
    ├── AI_RULES.md           本文件
    └── styles-index.json     所有主题注册表
```

## 给 AI 的指令示例

错误指令：
> 帮我在 kino 里加登录页

正确指令：
> 1. 在 `pages/login/` 新建登录页面
> 2. 引用 `components/button/button.css` 和 `styles/twilight/tokens.css`
> 3. 表单数据定义在 `pages/login/data/form-config.json`
> 4. 登录按钮使用 `<button class="btn btn-solid btn-md">登录</button>`
