# AGENTS.md - 项目工作手册 · MT-Visual-Language

> 本仓库 = HAE 个人设计系统的**唯一真源（Single Source of Truth）**。
> 不产出代码、不跑服务；交付物是 Markdown 设计规范的版本化沉淀。更新：2026-09-29

## 1. 项目定位

- 用途：为本机所有项目（MT-Deck、blog、未来 AI 工具）提供统一 UI 语言。下游项目**只读引用**本仓库，不在各自项目里维护规范副本。
- 核心资产：`HAE Creator Design System V0.1.md`（自包含终稿，可直接整份投喂 AI 编程助手）。
- 设计语言一句话：「无色世界中的一点原色」——纸感底、单点 accent、气声描边、无阴影、字重+对比度做层级。

## 2. 文件职责（单一职责，勿混写）

| 文件 | 职责 | 状态 |
|---|---|---|
| `HAE Creator Design System V0.1.md` | 规范本体：Tokens / Typography / Components / Interaction / AI 十条指令 | DECIDED（V0.1 基线） |
| `HAE Creator Design System - 设计逆向分析.md` | 证据链：40 套源配色的程序化统计，规范里每个数值的出处 | 保留，只增不删 |
| `README.md` | GitHub 仓库门面与总索引：这是什么、包含哪些文件、怎么用、设计立场 | — |
| `index.html` | 面向用户的产品介绍页（GitHub Pages 站点根即此页）：讲特点与观感、重美观，不堆技术细节。与 README 互补——README 是索引，index 是展示 | 展示物，随规范升版同步 |
| `decisions/` | 决策与外部方案评审记录：保留「方案→结论→原因」含落地勘误 | 只增不删 |
| `_scratch/` | 工作缓存（已 gitignore）：复算脚本 + rime-color-scheme 源克隆 + `proposals/` 外部提案原件 | 可再生产 |

## 3. 消费方式（写死，防漂移）

- 下游项目引用 = **一行指针**，不复制全文。示例（写进各项目的 AGENTS.md / CLAUDE.md / Cursor User Rules）：
  `UI 相关任务必读并遵守 E:\19 Python File\MT-Visual-Language\HAE Creator Design System V0.1.md`
- 仅当项目要交给外部协作者或离开本机时，才允许复制全文为该项目 DESIGN.md，并在复制处注明来源与日期。
- 指针依赖绝对路径：本目录改名/搬家时，须同步更新各工具里的指针。

## 4. 迭代规则

- Token 与规则**只在本仓库修改**；下游发现规范不好用 → 回到这里改终稿并升版本，不在下游打补丁。
- 每次升版：文件名带版本号（V0.1 → V0.2），旧版文件保留在本仓库作为历史；终稿内维护 Changelog。
- 决策状态标注沿用全局手册：DECIDED / EXPLORING / DEFERRED / REJECTED。当前：数据可视化色板、Figma 变量导出、多品牌换肤流水线 = DEFERRED（首个真实项目验证后再做）。
- 分析报告中的数值均可用 `_scratch/analyze_rime.py` 对源仓库复算；改规范前先看证据，别凭感觉。
- 外部 AI / 协作者提交的优化方案：先批判评审（对照 §5 红线、标 DECIDED/EXPLORING/DEFERRED/REJECTED），结论与理由记入 `decisions/日期_主题.md`，原始长文归档到 `_scratch/proposals/`（不入库）。**数值一律本地复算后再采纳，绝不采信外部报的数**（本项目唯一核心能力就是"可复算"，外部 AI 在此项上不可靠）。

## 5. 红线（继承全局 AGENTS.md，此处最相关三条）

- 不为完整性扩范围：本仓库拒绝在 V0.1 阶段生成**供下游消费的 CSS / Tailwind / 组件库 / Figma 导出产物**（DEFERRED）。注：`index.html` 是面向用户的可视化展示页、非上述工程产物，不受此条约束，勿误删。
- accent 插槽制：换主题只改 `--accent` 一族 4 值；永不修改品牌原色本身。
- 状态色与 accent 撞车（默认铁锈红 vs danger）是已知风险，落地项目时优先换非红系 accent，而不是加例外规则。
