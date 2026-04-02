---
theme: default
title: 你的汇报标题
info: |
  NJU-inspired light academic Slidev template.
colorSchema: light
drawings:
  persist: false
mdc: true
lineNumbers: false
fonts:
  sans: Source Han Sans SC, PingFang SC, Microsoft YaHei, sans-serif
  serif: Source Han Serif SC, Songti SC, STSong, serif
  mono: JetBrains Mono, Menlo, monospace
defaults:
  layout: nju-default
  transition: fade-out
layout: nju-cover
speaker: 汇报人姓名
affiliation: 南京大学某某学院
mentor: 导师：导师姓名
date: 2026.03
---

---
title: 报告提纲
---

<div class="nju-outline-wrap">
  <div class="nju-outline-note">本次汇报按照问题、方法、结果三部分展开。</div>
  <div class="nju-outline-grid">
    <div class="nju-outline-card">
      <div class="nju-outline-index">PART 01</div>
      <h3 class="nju-outline-title">研究背景</h3>
      <p class="nju-outline-copy">交代研究问题的来源与科学意义。</p>
    </div>
    <div class="nju-outline-card">
      <div class="nju-outline-index">PART 02</div>
      <h3 class="nju-outline-title">研究方法</h3>
      <p class="nju-outline-copy">说明研究思路、技术路线与关键参数。</p>
    </div>
    <div class="nju-outline-card">
      <div class="nju-outline-index">PART 03</div>
      <h3 class="nju-outline-title">结果与结论</h3>
      <p class="nju-outline-copy">展示关键结果，归纳主要结论。</p>
    </div>
  </div>
</div>

---
layout: nju-section
title: 研究背景
---

---
title: 研究背景
---

::div{class="grid grid-cols-[1.12fr_0.88fr] gap-4 pt-1 items-start"}
::div{class="space-y-4"}
<div class="nju-callout">
  <strong>为什么关注这个问题</strong>
  <p>简要说明研究对象的重要性与研究价值，交代领域背景与现有工作的局限性。</p>
</div>

::div{class="nju-note-box nju-compact-list"}
**核心问题**

- 现有研究还缺少什么？
- 你的工作解决哪个关键科学问题？
- 预期会带来什么样的科学意义？
::
::

::div{class="space-y-3"}
<NjuMetric label="研究对象" value="your system" hint="替换为你的研究体系或材料" />
<NjuMetric label="核心变量" value="key variable" hint="替换为你关注的核心物理量或参数" />
::
::

---
title: 研究问题与目标
---

<div class="grid grid-cols-2 gap-4 pt-3">
  <NjuStep index="01" title="目标一" body="简要描述第一个研究目标，说明希望回答的科学问题。" />
  <NjuStep index="02" title="目标二" body="简要描述第二个研究目标，说明希望实现的技术或方法突破。" />
  <div class="col-span-2">
    <NjuStep index="03" title="目标三" body="简要描述第三个研究目标，说明整体工作对领域的潜在贡献。" />
  </div>
</div>

---
layout: nju-section
title: 研究方法
---

---
title: 整体研究流程
---

<div class="grid grid-cols-2 gap-3 pt-2">
  <NjuStep index="01" title="步骤一" body="描述第一步研究工作，例如数据准备、实验设计或模型构建。" />
  <NjuStep index="02" title="步骤二" body="描述第二步研究工作，例如方法实施、计算或测量过程。" />
  <NjuStep index="03" title="步骤三" body="描述第三步研究工作，例如数据处理、分析或验证。" />
  <NjuStep index="04" title="步骤四" body="描述第四步研究工作，例如结果提取、对比或总结。" />
</div>

---
title: 方法与参数设置
---

::div{class="grid grid-cols-[0.92fr_1.08fr] gap-5 pt-2 items-start"}
::div{class="space-y-4"}
<div class="nju-callout">
  <strong>核心方法说明</strong>
  <p>简要说明本工作采用的研究方法，以及选择该方法的依据。</p>
</div>

::div{class="nju-math-block"}
$$
y = f(x; \theta)
$$
::

::div{class="nju-note-box"}
汇报时优先交代方法选择的理由与关键假设，推导细节可留至补充页。
::
::

::div{class="nju-table-wrap"}
<table>
  <thead>
    <tr>
      <th>项目</th>
      <th>设置</th>
      <th>说明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>参数一</td>
      <td>值 / 范围</td>
      <td>说明该参数的物理含义或选取依据</td>
    </tr>
    <tr>
      <td>参数二</td>
      <td>值 / 范围</td>
      <td>说明该参数的物理含义或选取依据</td>
    </tr>
    <tr>
      <td>参数三</td>
      <td>值 / 范围</td>
      <td>说明收敛性或稳定性的验证方式</td>
    </tr>
    <tr>
      <td>输出量</td>
      <td>物理量列表</td>
      <td>列出本工作关注的核心输出物理量</td>
    </tr>
  </tbody>
</table>
::
::

---
layout: nju-section
title: 结果与结论
---

---
title: 关键结果
---

<div class="nju-figure pt-1">
  <div class="nju-figure-title">图 1. 关键结果区</div>
  <div class="grid grid-cols-2 gap-4">
    <div class="nju-plot-placeholder">插入图片一：主要结果图，如曲线、分布图或热图</div>
    <div class="nju-plot-placeholder">插入图片二：辅助分析图，如对比图或机制示意图</div>
  </div>
</div>

<div class="grid grid-cols-3 gap-3 pt-3">
  <NjuMetric label="指标一" value="X.XX unit" hint="替换为关键量化结果，例如准确率、能量差或效率" />
  <NjuMetric label="指标二" value="X.XX unit" hint="替换为另一核心指标" />
  <NjuMetric label="指标三" value="X.XX unit" hint="替换为补充指标" />
</div>

---
title: 机制讨论
---

::div{class="grid grid-cols-2 gap-3 pt-2 items-start"}
::div{class="nju-panel nju-panel-compact"}
### 现象描述

描述你在数据或结果中观察到的主要规律，避免直接重复图的内容，而是提炼核心模式。
::

::div{class="nju-panel nju-panel-compact"}
### 机制解释

从物理图像或理论角度解释为什么会出现上述规律，指出最关键的驱动因素。
::

::div{class="col-span-2 nju-panel nju-panel-compact"}
### 综合判断

将以上观察与机制整合为一个统一的科学结论，并说明其对领域的意义或后续工作的指导价值。
::
::

---
title: 结论
---

<div class="nju-conclusion-stack">
  <div class="nju-conclusion-group">
    <h3>主要结论</h3>
    <ul>
      <li>请在此填写第一条核心结论，说明最重要的科学发现。</li>
      <li>请在此填写第二条核心结论，说明主要机制或规律。</li>
      <li>请在此填写第三条核心结论，说明对领域的理论或应用价值。</li>
    </ul>
  </div>

  <div class="nju-conclusion-group">
    <h3>下一步工作</h3>
    <ul>
      <li>请在此填写近期计划，例如扩展体系、提升精度或实验验证。</li>
      <li>请在此填写远期方向，例如高通量筛选、与其他方法结合或应用落地。</li>
    </ul>
  </div>
</div>

---
layout: nju-end
title: 感谢聆听
---
