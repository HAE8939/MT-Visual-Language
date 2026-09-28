# MT-Visual-Language

HAE 个人 AI 产品设计系统 · 唯一真源仓库。

这里存放的不是某个产品的代码，而是一套**跨项目复用的 UI 设计语言**：任何项目要做界面，先来这里读规范。目标是让 MT-Deck、博客、未来的 AI 工具在视觉上像"同一家人"——纸感背景、单一高饱和 accent、气声描边、无阴影、层级靠字重与对比度。

## 内容

```
HAE Creator Design System V0.1.md        ← 规范本体（自包含，可直接投喂 AI 编程助手）
HAE Creator Design System - 设计逆向分析.md  ← 证据链（40 套源配色的程序化统计）
AGENTS.md                                ← 仓库维护规则（真源原则、指针引用、版本迭代）
```

## 起源

对开源项目 [nevertoday/rime-color-scheme](https://github.com/nevertoday/rime-color-scheme)（MIT）做**设计逆向分析**：解析其全部 40 套配色方案（20 主题 × 浅色/夜色）的 YAML 色值，提炼出可迁移的设计规律——

- 品牌原色在浅色/夜色中一个字节都不改（20/20）
- 全画面只允许一个高饱和色，其余皆为带色温的中性灰
- 层级用对比度分档（正文 ≈11:1 / 次级 ≈4.5:1 / 描边 ≈1.15:1），不靠字号与粗线
- 暗色分层用半透明白叠加（7%）代替阴影
- 选中块前景按亮度自适应（白字 or 同系深墨）

产出的《HAE Creator Design System》是受其启发、面向 AI 软件（对话界面、Prompt/资产管理器、创作工作台）的**原创设计系统**，非该主题复制品。

## 怎么用

**给 AI 编程助手**：把 `HAE Creator Design System V0.1.md` 整份放进项目上下文，或在项目 AGENTS.md 里加一行指针：

```
UI 相关任务必读并遵守 <本仓库路径>/HAE Creator Design System V0.1.md
```

**给人**：直接读终稿；想知道"规则为什么这么定"，查分析报告的数据附录。

## License

规范文本 CC0 / MIT 任选（自用无约束）；分析对象代码版权归原项目（MIT）。
