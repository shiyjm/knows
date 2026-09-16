---
title: ChatGPT Work、GitHub 与 Google Drive 的个人知识工作流
updated: 2026-09-16
tags:
  - chatgpt
  - work
  - github
  - codex
  - google-drive
  - obsidian
  - knowledge-management
---

# ChatGPT Work、GitHub 与 Google Drive 的个人知识工作流

## 1. 核心结论

个人 AI 工具链采用“文件真源、知识真源、代码真源”三层分工：

- **Google Drive：正式文件真源**
- **GitHub `knows`：Markdown 知识真源**
- **独立 GitHub 代码账号及项目仓库：代码真源**

ChatGPT Chat / Work 负责研究、讨论、分析和知识蒸馏；Codex 负责代码开发；Obsidian 仅作为 Markdown 知识库的本地阅读与编辑界面，不再建立另一套独立知识源。

---

## 2. ChatGPT Web Work 与 Desktop Work 的分工

### ChatGPT Web / Cloud Work

适合：

- 网络研究与资料检索；
- Google Drive 文件搜索、阅读、处理；
- 长时间云端任务；
- 本机关闭后继续执行的任务；
- 与 GitHub 知识库交互；
- 将对话和研究结论沉淀为 Markdown。

### ChatGPT Desktop Work

适合：

- 本地文件；
- iCloud Drive；
- PDF、Word、PPT、Excel；
- 桌面应用；
- 本地浏览器协作；
- 需要直接操作 Mac / Windows 文件系统的任务。

原则：**希望电脑关机后继续执行，优先 Cloud Work；需要直接处理本地文件和桌面应用，优先 Desktop Work。**

---

## 3. Google Drive 的定位

Google Drive 不承担个人知识库职责，而是作为正式项目文件的唯一云端文件源。

适合保存：

- PDF；
- Word；
- PowerPoint；
- Excel；
- 扫描件；
- 图片、视频；
- 论文原文；
- 项目申报材料；
- Google Docs / Sheets / Slides 工作稿。

推荐原则：

- Google 原生格式适合作为 Working；
- Office / PDF 适合作为 Release；
- 不再为 ChatGPT 单独复制一套“资料库文件”。

ChatGPT Project 主要保存项目背景、长期规则、讨论历史和决策上下文，而不是承担文件仓库职责。

---

## 4. GitHub `knows` 的定位

`knows` 用作长期个人知识库，只存放适合版本化维护的轻量知识资产。

适合保存：

- Markdown；
- Prompt；
- 方法论；
- 决策记录；
- 技术架构；
- 工具使用规范；
- 项目总结；
- 研究结论；
- 少量 TXT / YAML / JSON 等文本文件。

不适合保存：

- 大型 PDF；
- Word / PPT / Excel；
- 视频；
- 大量原始论文附件；
- 大型数据集。

知识库的目标不是“聊天归档”，而是：

> ChatGPT 对话 / Work 研究 → 知识蒸馏 → Markdown → GitHub

---

## 5. 什么内容值得沉淀

优先保存三类内容：

1. **结论**：最终决定采用什么；
2. **方法**：以后可以重复使用的流程、框架、Prompt；
3. **知识**：研究结论、技术架构、经验总结。

一般不保存：

- 聊天流水账；
- 反复试探过程；
- 临时想法；
- 已被否决方案的大段过程；
- 简单事实型问答。

### 快捷指令约定

正式约定以下指令：

> **沉淀本次对话到 knows。**

其默认含义为：

1. 提炼当前对话中具有长期价值的结论、方法和知识；
2. 先搜索 `shiyjm/knows` 是否已有同主题 Markdown；
3. 已有同主题条目时优先合并更新，不重复创建近似文件；
4. 没有合适条目时才新建 Markdown；
5. 不保存聊天流水账、临时试探过程或隐藏推理；
6. 保持已有知识结构和命名风格，必要时更新 `updated` 日期；
7. 直接提交到 GitHub；
8. 完成后报告更新/新增的文件路径和 commit SHA。

该指令的目标是让 `knows` 成为**持续演化的知识库**，而不是对话备份仓库。

---

## 6. ChatGPT Web GitHub 与 Codex GitHub 的区别

### ChatGPT Web + GitHub

更适合：

- 搜索仓库；
- 阅读文件；
- 创建、更新和删除 Markdown；
- 维护 README；
- 维护知识条目；
- 查看和管理 Issue / PR；
- 小规模文本配置修改。

### Codex + GitHub

更适合：

- 多文件代码修改；
- 重构；
- `git diff` / `git status` / `git log`；
- shell 命令；
- 安装依赖；
- 编译；
- 测试；
- lint；
- type check；
- debug；
- 创建开发分支和 PR。

判断规则：

> **文件内容本身是工作对象，用 ChatGPT Web；整个 repository 是需要运行、测试和迭代的软件工程环境，用 Codex。**

---

## 7. 两个 GitHub 账号的隔离方案

采用两个 GitHub 账号：

### 账号 A：Knowledge

用途：

- 只保存知识库；
- ChatGPT Web Chat / Work 连接；
- 主要仓库：`shiyjm/knows`；
- 默认由 ChatGPT Web 负责写入。

### 账号 B：Development

用途：

- 保存代码项目；
- Desktop Codex 使用；
- clone / edit / test / commit / push / PR；
- 不作为 ChatGPT Web 知识沉淀目标。

账号级隔离可以减少误写代码仓库的风险，并形成明确的最小权限边界。

---

## 8. 多工具不冲突的规则

### 规则 1：知识库与代码库分开

不要把知识和代码塞进同一个“大仓库”。

### 规则 2：唯一主写者

- `knows`：ChatGPT Web 为主写者；
- 代码仓库：Codex 为主写者。

### 规则 3：Desktop Work 不成为第三个 Git 主写者

Desktop Work 主要面向 Google Drive、本地文件、iCloud 和 Office 文件。

### 规则 4：同一文件同时只由一个端编辑

如果 Obsidian 本地编辑 `knows`，先 `git pull`；编辑完成后再 commit / push。

### 规则 5：复杂并行修改才使用 branch / PR

个人知识库日常更新可直接维护默认分支；只有复杂修改、多人或多 Agent 并行时再使用分支和 PR。

---

## 9. Obsidian 的定位

Obsidian 不再作为独立知识源，而只是 GitHub Markdown 知识库的本地界面。

推荐结构：

```text
GitHub: shiyjm/knows
        ↕ git pull / push
Mac 本地 clone
        ↕
Obsidian Vault
```

因此：

> GitHub Repository = Markdown Knowledge Base = Obsidian Vault

避免 GitHub、Obsidian、Notion、Evernote、Mem 各维护一份知识。

---

## 10. 推荐的最终工具链

```text
                         ChatGPT
                     Chat / Web Work
                          │
              ┌───────────┴───────────┐
              ↓                       ↓
       GitHub Knowledge          Google Drive
        shiyjm/knows            正式文件真源
              │                       │
         Markdown             PDF / Word / PPT
              │                 Excel / 原始资料
              ↓
           Obsidian
          可选本地界面


Desktop Codex
      │
      ↓
GitHub Development Account
      │
      ↓
独立代码项目仓库
```

最终只保留三个“真源”：

1. **Google Drive = 文件真源**
2. **GitHub `knows` = 知识真源**
3. **GitHub Development Repositories = 代码真源**

---

## 11. 当前实施决策

- 不引入 Mem 作为主知识库；
- 不再引入 Notion / Evernote 作为另一套个人知识系统；
- GitHub Free 足以支撑当前个人 Markdown 知识库需求；
- `shiyjm/knows` 作为 ChatGPT Web 的知识沉淀仓库；
- Google Drive 继续存放正式文档与项目原始文件；
- Codex 使用独立 GitHub 账号管理代码仓库；
- Obsidian 后续可直接打开 `knows` 的本地 clone 作为 Vault；
- “沉淀本次对话到 knows。”作为后续知识沉淀的标准快捷指令。

该架构的目标是：**工具尽量少、真源清晰、权限隔离、AI 可直接读写、长期可版本化维护。**
