# 标准组件与 DOM 契约

精确尺寸、颜色和间距以仓库的 `assets/infra-visual-note.css` 为准。将以下结构与 `assets/components.html` 对照使用。

| 组件 | 直接结构 | 核对项 |
| --- | --- | --- |
| 契约头 | `.ivn-header` 包含 `.ivn-kicker`、H1、`.ivn-subtitle`、`.ivn-jump`、`.ivn-spec` | 每个链接包含 `.ivn-num`，编号与对应章节完全一致。键值条用 `dl > div > dt + dd` |
| 章节 | `section.ivn-section[id]` 依次放 `.ivn-sec-head`、`.ivn-lead` 和内容 | `.ivn-sec-head` 里是 `.ivn-sec-index` 与 H2。导语 2–4 句 |
| 卡片网格 | `.ivn-scroll > .ivn-grid-2/.ivn-grid-3/.ivn-grid-4 > .ivn-card` | 卡的语义由 `data-tone` 和 `.ivn-badge` 同时标明 |
| 手算工作台 | `.ivn-scroll > .ivn-workbench > .ivn-wb-panel` | 两侧各含 `.ivn-wb-head`、维度公式、手算行和 `.ivn-res`。项为 `.ivn-term > .ivn-expr + .ivn-dim`，运算符为 `.ivn-op` |
| 一体化泳道 | `.ivn-scroll > .ivn-swimlane-board > .ivn-lane-headers + .ivn-stage…` | 每阶段为 `.ivn-stage-bar` 和 `.ivn-stage-cols`，三列为 `.ivn-lane-cell`、`.ivn-lane-mid`、`.ivn-lane-cell`。中列 240px。跨设备阶段用 `data-phase="comm"` 与 `.ivn-comm-pill` |
| 槽位 | `.ivn-slots > .ivn-slot` | 用 `.is-masked` 标记 padding 或遮罩。槽位顺序和组边界须与算子一致 |
| 流水线 | `.ivn-scroll > ol.ivn-pipeline[data-steps] > li.ivn-card` | 3、4 或 5 步。每卡含编号徽章、步骤名、接口与动作理由 |
| 账本 | `.ivn-scroll > table.ivn-ledger` | 数字列用 `.ivn-num-col`。优选行加 `data-tone="green"`，附适用条件与计量口径 |
| 洞察与结尾 | `.ivn-callout > .ivn-callout-tag`，全文最后为 `.ivn-takeaway > .ivn-takeaway-mark + p` | 洞察条标明为何应关注。闭环卡落回全文的技术因果 |

**宽图**使用 `role="region"`、`aria-label`、`tabindex="0"` 及 `data-width="780"` 或 `data-width="860"`。需要绘制精确硬件拓扑时，可直接放含内联 SVG 的 `figure`，通过 viewBox、CSS 颜色变量和文字标签表达连线。节点与示意方向可由 `title`、`desc` 和 SVG 文本读出。

**轻量数学**用 `.ivn-math`、`i`、`sub`、`sup` 表示行内公式。算子前后的形状放入 `.ivn-dim-formula`，手算写在 `.ivn-calc-row`。矩阵 `.ivn-mat` 按行展开子单元，`data-cols` 取 1–4。给矩阵提供可读的无障碍标签。泳道伪代码用 `pre.ivn-code > code`，每行调用标明输入输出形状或紧邻的 shape 注释。
