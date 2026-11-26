---
name: infra-visual-note
description: 用工程图解讲义风（Infra Visual Note）编写、改版和审查静态 HTML 技术笔记。适用于模型架构、数学与张量推导、GPU 互联、分布式并行与多设备数据流。
---

# 工程图解讲义风（Infra Visual Note）

把同一模块的因果、签名、形状和数值放在一起。左右表示对照与对等 Rank，上下表示执行顺序，中轴表示算子、位置不变量或通信契约。

## 规划与交付

1. 先固定全篇的符号、行向量方向、玩具数字、Rank 归属、拓扑、精度与工程规模。把适用项放进顶部 Spec Bar。区分实测、估算和线速上限。
2. 每节先用 2–4 句导语说明约束和结果，再给对应图解。逐项核算公式的内侧消去维度、输入输出形状和同一组手算结果。注明有意保留的历史算例与主算例之间的差异。
3. 用[组件参考](references/components.md)选型，复制[可运行模板](assets/components.html)中对应的结构。文章放在 `notes/<slug>/index.html`，只引用 `../../assets/infra-visual-note.css`。以[公共 CSS](../../../assets/infra-visual-note.css)为像素、变量和类名的唯一来源。
4. 检查通信组、scatter/gather 轴、每 Rank 收发量及反向转置、掩码、Shift、梯度归约边界。账本注明单位、dtype 和计数范围，将临时、常驻、预计算与稳态区分开。
5. 执行[交付自检](references/checklist.md)。内页与读者外壳分别职责明确。在桌面、390px、768px 和打印视图中确认定位与宽图几何。

## 结构与约束

- `<body class="ivn">` 内只放 `.ivn-canvas`。契约头之后，每个 `.ivn-section` 有唯一 ID、编号 `.ivn-sec-index` 和 `.ivn-lead`，对应顶部锚点的同号 `.ivn-num`。最后一个组件是 `.ivn-takeaway`。
- 在 `.ivn-scroll` 的第一层直接放标准网格、手算台、泳道、流水线、账本或 SVG figure。只选 780px 或 860px；不套额外白框。
- 双栏推导用 `.ivn-workbench`、`.ivn-dim-formula`、`.ivn-mat`。长公式行内使用 `.ivn-math` 和 HTML 上下标。贯通泳道必须以 `.ivn-lane-headers` 开头，每阶段只用左右设备与中轴契约三列。使用 `data-phase="comm"` 或 `data-phase="out"` 标明跨卡与输出阶段。
- 蓝表示输入与常规归属，绿表示等价、收益和输出，琥珀表示边界与瓶颈，红表示反例，紫只表示跨设备通信。对等 Rank 保持同一浅蓝底色，靠位置、编号、文字区分。紫色阶段的自动高亮只落在阶段号和中轴，两侧保持同色。
- 禁止页面私有类、私有选择器、额外样式表、内联样式、裸 MathML、Emoji 和手写 `<br>`。保留原有引文与技术结论。旧图拆成标准组件，保留有语义的方向、归属、次序与关系。

## 外层目录登记规则

- 新增笔记后，在根目录 `index.html` 的对应一级领域 `.nav-domain > ul.nav-list` 下直接追加一条。关键词覆盖常用缩写、英文术语与中文同义词，`href` 与 `data-chapter` 使用同一个 slug。

  ```html
  <li class="nav-item" data-keywords="术语 缩写 中文关键字">
    <a class="nav-link" href="./notes/<slug>/" data-chapter="<slug>" target="chapter-content">
      <span class="nav-title">标题</span>
    </a>
  </li>
  ```

- 同步更新一级块头部的 `.nav-domain-count` 和侧栏页脚的 `.reader-note-total`。目录常驻全展开，一级领域与条目直接相连。禁止使用 `<details>`、`<summary>` 或插入二级子文件夹标题。
- 保持切换、`?chapter=<slug>` 直达和浏览器历史使用同一个 `data-chapter`，复验搜索、面包屑和窄屏抽屉。目录、搜索和面包屑放在外层阅读器。
