# 南京大学 Slidev 学术 PPT 开发文档

## 1. 文档目标

这份文档用于说明当前项目如何作为一套可维护、可扩展的 Slidev 学术汇报模板来使用与继续开发。

它面向三类场景：

- 直接拿现有模板写一份新的学术汇报
- 在现有风格上继续优化封面、章节页、正文页和结束页
- 把这套模板继续整理成可复用的 Slidev 主题

当前模板的定位不是通用商务演示，而是：

- 南京大学风格
- 浅色主题
- 学术简洁
- 适用于理学、工学类研究汇报（组会、开题、中期、答辩）

## 2. Slidev 中“模板”的含义

如果从 PowerPoint 的角度理解，Slidev 的模板能力主要由下面几部分组成：

- `theme`
  主题，负责整套视觉风格与默认行为
- `layouts`
  页面母版，负责封面页、章节页、正文页、结束页的结构
- `components`
  可复用内容模块，负责指标卡、步骤卡、品牌角标等
- `styles`
  全局样式，负责颜色、字体、边框、阴影、间距
- `slides.md`
  当前这次汇报的实际内容

也就是说，Slidev 是“代码化模板”，而不是 PowerPoint 那种完全可视化母版。

优点是：

- 风格可以完全统一
- 修改一次，整套页面都会同步更新
- 很适合科研汇报这种结构相对稳定的内容

## 3. 当前项目目录

```text
nju-slidev-template/
├─ components/
│  ├─ NjuBrand.vue
│  ├─ NjuMetric.vue
│  ├─ NjuStep.vue
│  └─ NjuTag.vue
├─ docs/
│  └─ PPT开发文档.md
├─ layouts/
│  ├─ nju-cover.vue
│  ├─ nju-default.vue
│  ├─ nju-section.vue
│  └─ nju-end.vue
├─ public/
│  └─ assets/
│     └─ nju-badge-transparent.png
├─ setup/
│  └─ katex.ts
├─ styles/
│  └─ index.css
├─ slides.md
├─ package.json
└─ README.md
```

各目录作用如下：

- `slides.md`
  当前 PPT 的实际内容入口
- `layouts/`
  页面结构层
- `components/`
  可复用内容组件层
- `styles/index.css`
  全局视觉规范层
- `public/`
  Logo、校标、静态图形资源
- `setup/katex.ts`
  公式渲染配置

## 4. 当前模板结构

默认汇报结构如下：

1. 封面
2. 报告提纲
3. 第一章章节页：研究背景
4. 研究背景
5. 研究问题与目标
6. 第二章章节页：研究方法
7. 整体研究流程
8. 方法与参数设置
9. 第三章章节页：结果与结论
10. 关键结果
11. 机制讨论
12. 结论
13. 感谢聆听

这套结构适合以下类型的汇报：

- 组会进展汇报
- 开题 / 中期报告
- 学术会议报告
- 毕业论文答辩

## 5. 如何运行

如果终端里没有 `node/npm`（macOS + Homebrew 环境），先执行：

```bash
export PATH="/opt/homebrew/bin:$PATH"
```

安装依赖：

```bash
npm install
```

开发预览：

```bash
npm run dev
```

构建：

```bash
npm run build
```

导出 PDF：

```bash
npm run export
```

## 6. 如何修改汇报内容

### 6.1 修改封面

直接改 [slides.md](../slides.md) 顶部的封面 frontmatter：

```yaml
---
layout: nju-cover
title: 你的汇报标题
speaker: 姓名
affiliation: 南京大学某某学院
mentor: 导师：导师姓名
date: 2026.03
---
```

常改字段：

- `title`
  汇报标题
- `speaker`
  汇报人
- `affiliation`
  单位或院系
- `mentor`
  导师信息
- `date`
  日期

### 6.2 修改正文标题

每页的标题来自该页 frontmatter 里的 `title`。

例如：

```yaml
---
title: 机制讨论
---
```

### 6.3 修改结论页

当前结论页是从上到下的条目式结构，内容在 [slides.md](../slides.md) 末尾部分。

建议写法：

- 第一条写最重要的物理发现
- 第二条写机制解释
- 第三条写理论意义或设计意义
- 下一步工作只写 1 到 2 条

## 7. 页面布局说明

### 7.1 `nju-cover`

文件：

- [layouts/nju-cover.vue](../layouts/nju-cover.vue)

作用：

- 封面页
- 左侧标题与作者信息
- 右上角统一品牌角标
- 背景使用淡化校标水印

适合放：

- 标题
- 姓名
- 单位
- 导师
- 日期

### 7.2 `nju-default`

文件：

- [layouts/nju-default.vue](../layouts/nju-default.vue)

作用：

- 绝大多数正文页
- 左上正文标题
- 右上统一品牌角标
- 右下角日期

适合放：

- 提纲页
- 背景页
- 方法页
- 结果页
- 讨论页
- 结论页

### 7.3 `nju-section`

文件：

- [layouts/nju-section.vue](../layouts/nju-section.vue)

作用：

- 各章节的封面页
- 居中标题
- 中心淡化校标水印
- 适合作为章节切换

建议每一个大章节开始前都插入一页。

### 7.4 `nju-end`

文件：

- [layouts/nju-end.vue](../layouts/nju-end.vue)

作用：

- 汇报结束页
- 仅保留“感谢聆听”
- 背景校标水印居中
- 视觉简洁，不再放邮箱和英文副标题

## 8. 组件说明

### 8.1 `NjuBrand`

文件：

- [components/NjuBrand.vue](../components/NjuBrand.vue)

作用：

- 统一右上角南京大学品牌角标
- 所有页面使用同一个组件

如果后续要统一改 logo 大小、文字、位置，优先改这个组件和全局 CSS。

### 8.2 `NjuMetric`

文件：

- [components/NjuMetric.vue](../components/NjuMetric.vue)

作用：

- 展示一个核心指标
- 适合结果页放 2 到 4 个关键数值

例如：

```md
<NjuMetric label="势垒高度" value="0.18 eV" hint="示例指标，可替换为实际滑移能垒" />
```

### 8.3 `NjuStep`

文件：

- [components/NjuStep.vue](../components/NjuStep.vue)

作用：

- 展示一条技术路线或研究步骤
- 适合“研究路线”“技术框架”“工作流”

例如：

```md
<NjuStep index="01" title="结构建模" body="建立候选堆垛构型，并设置滑移路径或采样网格。" />
```

### 8.4 `NjuTag`

文件：

- [components/NjuTag.vue](../components/NjuTag.vue)

作用：

- 保留的小型标签组件
- 当前模板中已经尽量少用，避免装饰过多

## 9. 样式系统说明

主样式文件：

- [styles/index.css](../styles/index.css)

### 9.1 颜色变量

当前主题色基于以下变量：

- `--nju-plum`
  南京大学主色调紫红
- `--nju-plum-deep`
  更深的标题色
- `--nju-muted`
  次级说明文字
- `--nju-bg`
  页面背景
- `--nju-surface`
  卡片背景

如果你想整体换视觉风格，优先改 `:root` 里的这些变量，而不是到处改单独颜色。

### 9.2 统一品牌位置

右上角品牌现在由 `.nju-brand` 控制。

这保证了：

- 封面
- 章节页
- 正文页
- 结束页

的位置全部一致。

### 9.3 章节页背景

章节页的中心校标水印由 `.nju-section-watermark` 控制。

如果你想更明显一点，可以适当提高：

```css
opacity: 0.04;
```

如果你想更克制，可以进一步降低。

### 9.4 结束页背景

结束页的居中 logo 由 `.nju-end-watermark` 控制。

如果你觉得太大或太淡，可以调：

- `width`
- `opacity`

## 10. 字体如何统一

Slidev 支持直接在头部 frontmatter 配置字体。

当前 [slides.md](../slides.md) 已经配置了：

```yaml
fonts:
  sans: Source Han Sans SC, PingFang SC, Microsoft YaHei, sans-serif
  serif: Source Han Serif SC, Songti SC, STSong, serif
  mono: JetBrains Mono, Menlo, monospace
```

当前策略是：

- 标题使用衬线字体
- 正文使用无衬线字体
- 代码或公式辅助文字使用等宽字体

如果后续要完全切到本地字体，也可以继续用 Slidev 的 `fonts` 配置。

## 11. 公式、表格、图片的建议

### 11.1 公式

配置文件：

- [setup/katex.ts](../setup/katex.ts)

建议：

- 一页最多保留 1 到 2 个关键公式
- 只展示后文会用到的公式
- 推导过程放补充页，不放正文主线

### 11.2 表格

建议：

- 一页只交代最关键计算参数
- 表头尽量短
- 每列只负责一个维度

当前模板里的“计算设置与关键参数”页就是参考写法。

### 11.3 图片

对于理论计算汇报，优先级建议如下：

1. 主要结果图（曲线、分布图、热图等）
2. 辅助对比图
3. 机制示意图
4. 误差 分析图

不要在同一页同时堆太多图。

## 12. 面向理论计算汇报的推荐写法

### 12.1 背景页

建议回答三个问题：

- 为什么这个体系值得研究？
- 现有理论工作还缺什么？
- 你的工作切入点是什么？

### 12.2 计算框架页

建议回答：

- 用什么模型
- 用什么泛函
- 如何处理范德华作用
- 如何做滑移采样
- 最终输出哪些物理量

### 12.3 结果页

建议不要写成“图很多、解释很少”。

更推荐：

- 左边放图
- 右边放 2 到 3 个结论
- 底部放 2 到 3 个关键数值

### 12.4 讨论页

讨论页不是重复讲图，而是回答：

- 为什么会这样？
- 哪个机制最关键？
- 结论对后续材料设计有什么意义？

## 13. 如何新增页面

### 13.1 新增一页正文

```md
---
title: 新页面标题
---

这里写内容
```

### 13.2 新增一页章节页

```md
---
layout: nju-section
title: 新章节标题
---
```

### 13.3 新增一页结束页

```md
---
layout: nju-end
title: 感谢聆听
---
```

## 14. 如何继续把它做成真正的可复用主题

当前项目已经接近“主题”的形态，但仍然是一个模板项目。

如果后续要变成真正的 Slidev theme，建议做这几件事：

1. 把 `layouts/`、`components/`、`styles/`、`public/` 整理成标准主题结构
2. 增加 `package.json` 中的 theme 元信息
3. 提供一份最小 `example.md`
4. 将“南京大学理论计算版”和“南京大学实验表征版”拆成两个分支主题

这样以后新建任何汇报，都可以直接复用。

## 15. 常见维护建议

- 先改 `slides.md` 内容，再考虑改样式
- 先改全局变量，再改单个页面的局部样式
- 避免在单页里写太多内联样式
- 保持章节页、正文页、结束页的视觉节奏一致
- 模板要服务内容，不要让装饰压过学术信息

## 16. 当前项目的维护入口

如果以后只记 4 个入口，记这几个就够了：

- [slides.md](../slides.md)
- [styles/index.css](../styles/index.css)
- [layouts/nju-section.vue](../layouts/nju-section.vue)
- [layouts/nju-cover.vue](../layouts/nju-cover.vue)

## 17. 后续可继续扩展的方向

- 增加“补充材料”专用布局
- 增加“单图放大页”布局
- 增加“计算流程图”专用布局
- 增加“论文答辩版”和“组会简报版”两套章节配色
- 真正封装成一个 Slidev theme 包

---

如果后续继续开发，建议把这份文档和模板一起维护，而不是只改代码不更新说明。这样模板才能真正长期复用。
