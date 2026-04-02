---
theme: default
title: 二维材料层间滑移性质研究
info: |
  NJU-inspired light academic Slidev template for theory, DFT, and computational materials talks.
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
speaker: 王苏云
affiliation: 南京大学物理学院
mentor: 导师：万建国
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
      <p class="nju-outline-copy">交代问题来源、科学意义与研究目标。</p>
    </div>
    <div class="nju-outline-card">
      <div class="nju-outline-index">PART 02</div>
      <h3 class="nju-outline-title">计算方法</h3>
      <p class="nju-outline-copy">说明结构建模、DFT 设置与关键参数。</p>
    </div>
    <div class="nju-outline-card">
      <div class="nju-outline-index">PART 03</div>
      <h3 class="nju-outline-title">结果与结论</h3>
      <p class="nju-outline-copy">展示关键结果，并归纳主要物理结论。</p>
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
  <strong>为什么关注层间滑移</strong>
  <p>对于双层或异质二维材料，微小滑移就可能改变轨道重叠、界面电荷转移与能带对齐，从而显著影响体系稳定性与电子性质。</p>
</div>

::div{class="nju-note-box nju-compact-list"}
**核心问题**

- 不同堆垛构型之间的势能差与滑移势垒如何分布。
- 层间位移如何调控带边位置、带隙与耦合强度。
- 能否用一套统一图景串联“构型 - 势能面 - 电子结构”。
::
::

::div{class="space-y-3"}
<NjuMetric label="研究对象" value="双层 / 异质二维材料" hint="可替换为 MoS2、WSe2、graphene-based 等体系" />
<NjuMetric label="核心变量" value="堆垛与滑移坐标" hint="registry、层间距、局域对称性共同决定耦合响应" />
::
::

---
title: 研究问题与目标
---

<div class="grid grid-cols-2 gap-4 pt-3">
  <NjuStep index="01" title="绘制滑移势能面" body="识别稳定堆垛、过渡路径与势垒高度，明确体系的几何与能量图景。" />
  <NjuStep index="02" title="解析电子结构响应" body="跟踪滑移过程中能带、态密度、电荷重排和层间耦合的系统变化。" />
  <div class="col-span-2">
    <NjuStep index="03" title="建立高效筛选策略" body="提炼可迁移描述符，为高通量计算或机器学习辅助建模提供基础。" />
  </div>
</div>

---
layout: nju-section
title: 计算方法
---

---
title: 整体计算流程
---

<div class="grid grid-cols-2 gap-3 pt-2">
  <NjuStep index="01" title="结构建模" body="建立候选堆垛构型，并设置滑移路径或采样网格。" />
  <NjuStep index="02" title="DFT 几何优化" body="完成原子弛豫与层间距校正，得到稳定构型与基态能量。" />
  <NjuStep index="03" title="电子结构计算" body="计算能带、态密度、电荷密度差和功函数等关键物理量。" />
  <NjuStep index="04" title="描述符与筛选" body="将 DFT 结果映射到可解释描述符，并为可选的 ML 加速做准备。" />
</div>

---
title: 模型与参数设置
---

::div{class="grid grid-cols-[0.92fr_1.08fr] gap-5 pt-2 items-start"}
::div{class="space-y-4"}
<div class="nju-callout">
  <strong>示意表达式</strong>
  <p>这一页只保留对后文结果有解释力的核心定义，例如滑移势能或层间结合能。</p>
</div>

::div{class="nju-math-block"}
$$
\Delta E(\mathbf{r}) = E(\mathbf{r}) - E_{\min}
$$
::

::div{class="nju-note-box"}
报告时优先说明泛函、范德华修正与采样策略，推导细节可以留给补充页。
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
      <td>交换-相关泛函</td>
      <td>PBE / HSE06</td>
      <td>根据精度需求选择基态或高精度电子结构计算</td>
    </tr>
    <tr>
      <td>范德华修正</td>
      <td>D3 / optB86b-vdW</td>
      <td>确保层间相互作用描述合理</td>
    </tr>
    <tr>
      <td>平面波与 k 点</td>
      <td>500 eV / 12 × 12 × 1</td>
      <td>需做截断能和 k 网格收敛性测试</td>
    </tr>
    <tr>
      <td>输出量</td>
      <td>势能面 / 能带 / 电荷差分</td>
      <td>用于构建滑移与电子结构之间的对应关系</td>
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
    <div class="nju-plot-placeholder">插入滑移势能面、稳定堆垛示意或路径能量曲线</div>
    <div class="nju-plot-placeholder">插入能带、态密度、电荷密度差或局域耦合分析图</div>
  </div>
</div>

<div class="grid grid-cols-3 gap-3 pt-3">
  <NjuMetric label="势垒高度" value="0.18 eV" hint="示例指标，可替换为实际滑移能垒" />
  <NjuMetric label="层间距变化" value="0.12 A" hint="反映滑移过程中的局域几何响应" />
  <NjuMetric label="带边移动" value="0.21 eV" hint="示例指标，可替换为带隙或能级偏移" />
</div>

---
title: 机制讨论
---

::div{class="grid grid-cols-2 gap-3 pt-2 items-start"}
::div{class="nju-panel nju-panel-compact"}
### 势能面特征

稳定构型附近的能量起伏较缓，但特定 registry 区域会出现明显势垒抬升，说明局域原子对位对滑移路径有主导作用。
::

::div{class="nju-panel nju-panel-compact"}
### 电子结构响应

滑移诱导的轨道重叠变化会同步改变带边位置与层间电荷转移，因此几何构型与电子性质不能割裂讨论。
::

::div{class="col-span-2 nju-panel nju-panel-compact"}
### 综合判断

真正决定体系性质的不是单一最稳定堆垛，而是整张滑移势能面与电子结构响应之间的协同演化关系。
::
::

---
title: 机器学习辅助筛选（可选）
---

<div class="grid grid-cols-2 gap-4 pt-2">
  <div class="nju-panel">
    <h3>输入特征</h3>
    <p>堆垛位移、层间距、局域配位、原子环境描述符，以及少量 DFT 先验物理量。</p>
  </div>
  <div class="nju-panel">
    <h3>预测目标</h3>
    <p>势垒高度、稳定构型排序、带边移动、层间耦合强度等可量化输出。</p>
  </div>
</div>

<div class="nju-note-box nju-compact-list mt-4">
**使用场景**

- 用少量 DFT 数据训练代理模型，先做粗筛。
- 将高价值候选重新回到 DFT 精算，保证物理可信性。
- 若本次汇报不包含 ML，可直接删除本页。
</div>

---
title: 结论
---

<div class="nju-conclusion-stack">
  <div class="nju-conclusion-group">
    <h3>主要结论</h3>
    <ul>
      <li>请在此填写关于滑移势能面与稳定堆垛的核心结论。</li>
      <li>请在此填写电子结构随滑移演化的关键发现。</li>
      <li>请在此填写对理论理解或材料设计的主要贡献。</li>
    </ul>
  </div>

  <div class="nju-conclusion-group">
    <h3>下一步工作</h3>
    <ul>
      <li>请在此填写更高精度计算、更多体系扩展或外场调控方向。</li>
      <li>请在此填写高通量筛选或机器学习辅助建模的推进计划。</li>
    </ul>
  </div>
</div>

---
layout: nju-end
title: 感谢聆听
---
