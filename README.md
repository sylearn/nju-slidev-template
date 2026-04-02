# 南京大学 Slidev 学术汇报模板

<p align="center">
  <img src="public/assets/nju-badge-transparent.png" alt="NJU Logo" width="80" />
</p>

<p align="center">
  <a href="https://sli.dev"><img src="https://img.shields.io/badge/Powered%20by-Slidev-1e6ddf?logo=slideshare&logoColor=white" alt="Slidev" /></a>
  <img src="https://img.shields.io/badge/Vue-3-42b883?logo=vue.js&logoColor=white" alt="Vue 3" />
  <img src="https://img.shields.io/badge/Language-Markdown%20%2F%20Vue-informational?logo=markdown" alt="Language" />
  <img src="https://img.shields.io/badge/Theme-NJU%20Academic-8B1A4A" alt="Theme" />
  <img src="https://img.shields.io/badge/License-MIT-green" alt="License" />
</p>

<p align="center">
  一套面向南京大学学术场景的 Slidev 演示文稿模板 · A Slidev presentation template for NJU academic use
</p>

---

## 特性

- 🎨 **南京大学视觉规范**：基于学校标准色（紫红 `--nju-plum`）与品牌元素
- 📐 **学术简洁风格**：浅色主题，排版克制，适合科研汇报
- 🖼️ **多种页面布局**：封面页、章节页、正文页、结束页
- 🧩 **可复用组件**：指标卡、步骤卡、标签等
- ➗ **公式支持**：内置 KaTeX 配置
- 📄 **一键导出 PDF**

## 快速开始

**安装依赖**

```bash
npm install
```

**启动预览**

```bash
npm run dev
```

**构建静态站点**

```bash
npm run build
```

**导出 PDF**

```bash
npm run export
```

> **提示**：如果终端里找不到 `node/npm`，macOS 用户可先执行：
> ```bash
> export PATH="/opt/homebrew/bin:$PATH"
> ```

## 项目结构

```text
nju-slidev-template/
├─ components/          # 可复用 Vue 组件（指标卡、步骤卡等）
├─ layouts/             # 页面布局（封面、章节、正文、结束）
├─ public/
│  └─ assets/           # 静态资源（logo 图片等）
├─ setup/               # Slidev 插件配置（KaTeX 等）
├─ styles/
│  └─ index.css         # 全局样式与设计 token
├─ docs/
│  └─ PPT开发文档.md     # 详细开发文档
├─ slides.md            # 演示文稿内容入口
└─ package.json
```

## 主要入口

| 文件 | 用途 |
|------|------|
| [slides.md](./slides.md) | 演示文稿内容（从这里开始写） |
| [styles/index.css](./styles/index.css) | 全局样式与配色变量 |
| [layouts/nju-cover.vue](./layouts/nju-cover.vue) | 封面布局 |
| [layouts/nju-section.vue](./layouts/nju-section.vue) | 章节页布局 |
| [layouts/nju-default.vue](./layouts/nju-default.vue) | 正文布局 |
| [layouts/nju-end.vue](./layouts/nju-end.vue) | 结束页布局 |

## 完整文档

详细说明见 [docs/PPT开发文档.md](./docs/PPT开发文档.md)，包含：

- 项目结构与 Slidev 模板机制说明
- 各布局与组件的使用方式
- 样式系统与设计 token
- 公式、图表建议
- 如何扩展为真正的 Slidev theme

## License

[MIT](./LICENSE)
