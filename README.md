# Fuxi Agent Loop Skill / 伏羲

[English](README.en.md) | 简体中文

**把模糊任务变成可验证的 Agent 工作循环。**

Fuxi 是一个轻量级 agent skill, 用来帮助 AI Agent 处理文件、工具、代码仓库、创作流程、研究任务和多 agent 交接时的真实工作。

它不是一个巨型提示词, 而是一层小型控制协议: 告诉 agent 什么时候先发现现状, 什么时候动手, 什么时候验证, 什么时候保存状态, 什么时候必须停下来等人确认。

## 为什么需要 Fuxi

很多长期任务失败, 不是因为某一次回答差, 而是因为工作循环失控:

- agent 还没看真实文件和来源, 就开始行动;
- 任务越做越散, 但没有明确下一个检查点;
- 同一个 agent 既生成结果, 又自己给自己验收;
- 关键决策和路径在新会话里丢失;
- 自动化还没跑过一次安全手动流程, 就直接开始长期运行。

Fuxi 把这些问题压成一个可复用的 loop contract。

## 功能解读

| 能力 | 实际变化 |
|---|---|
| 意图翻译 | 把粗糙的人类需求变成明确下一步。 |
| 源头优先 | 先检查文件、仓库、日志或文档, 再判断。 |
| 可控执行 | 用小步 loop turn 推进, 避免任务失控扩散。 |
| 交接清晰 | 人、工具、agent 都能拿到明确交付物。 |
| 独立验证 | 用证据验证结果, 而不是靠自信。 |
| 持久记忆 | 只保存决策、阻塞点、路径和下一步。 |
| 安全停止 | 遇到风险或不可逆动作时停在人工检查点。 |

## 适合场景

适合让 Fuxi 处理:

- 混乱项目清理;
- 反复运行的创作或写作流程;
- 多 agent 协作;
- 代码仓库检查和维护;
- 知识库去重和整理;
- 自动化方案设计;
- 每日或每周项目巡检;
- 用户说不清楚, 但又需要真实执行的任务。

## 不适合场景

不适合一次性问答、闲聊、很小的单点修改, 或不涉及状态、交接、验证、重复执行的任务。

## 下载与安装

### Codex / Claude Code / 通用 agent

1. 下载本仓库。
2. 把 `SKILL.md` 放进你的 agent skills 目录, 并命名为 `fuxi`。

目录示例:

```text
skills/
  fuxi/
    SKILL.md
```

如果你的 agent 支持共享技能目录, 也可以放在共享位置, 让多个 agent 读取同一个 `fuxi`。

### Windows 手动安装示例

```powershell
git clone https://github.com/jomashi/fuxi-agent-loop-skill.git
mkdir "$env:USERPROFILE\.codex\skills\fuxi" -Force
copy .\fuxi-agent-loop-skill\SKILL.md "$env:USERPROFILE\.codex\skills\fuxi\SKILL.md"
```

### macOS / Linux 手动安装示例

```bash
git clone https://github.com/jomashi/fuxi-agent-loop-skill.git
mkdir -p ~/.codex/skills/fuxi
cp fuxi-agent-loop-skill/SKILL.md ~/.codex/skills/fuxi/SKILL.md
```

如果你的 agent 使用的不是 Codex 目录, 把 `~/.codex/skills/fuxi` 换成对应平台的 skills 目录即可。

## 使用方式

安装后, 直接让 agent 使用 `fuxi`:

```text
Use fuxi to turn this messy project cleanup into a repeatable workflow.
```

```text
Use fuxi to coordinate several agents without losing state.
```

```text
Use fuxi to make this vague creative workflow safe to run every day.
```

```text
Use fuxi to inspect this repository, define the next handoff, and stop before risky changes.
```

中文也可以:

```text
用 fuxi 把这个混乱的工作流整理成可反复执行、可验证、可暂停的流程。
```

## 安装后验证

让 agent 执行一个低风险测试:

```text
Use fuxi to plan one safe loop turn for organizing a messy notes folder. Do not modify files.
```

理想输出应该包含:

- 目标;
- 需要检查的来源;
- 下一步行动;
- 验证方式;
- 停止条件;
- 不会直接删除或自动化执行。

## Loop Contract

每个 Fuxi 循环都要回答 8 个问题:

| 字段 | 问题 |
|---|---|
| Goal | 这个循环结束后应该得到什么有用状态? |
| Owner | 哪个 agent、工具或项目负责哪一部分? |
| Discovery | 必须检查哪些源文件、仓库、日志或文档? |
| Handoff | 下一个执行者应该拿到什么交付物? |
| Verification | 怎么用独立方式验证成功? |
| Memory | 哪些决策和状态需要保存到哪里? |
| Stop rule | 什么时候必须停止, 不能继续猜? |
| Budget | 本轮允许消耗多少时间、token、重试、文件或工具调用? |

## 设计原则

- 先跑一轮安全的手动 loop turn, 再谈自动化。
- 先检查真实来源, 不靠记忆或习惯判断。
- 生成和验证分开。
- 保存决策, 不保存噪音。
- 遇到风险、歧义或不可逆动作时停止。

## 文件结构

```text
fuxi-agent-loop-skill/
├── SKILL.md              # Agent 读取的技能主体
├── README.md             # 中文首页
├── README.en.md          # English README
├── README.zh-CN.md       # 中文说明副本
├── ACKNOWLEDGEMENTS.md   # 来源与致谢说明
├── SECURITY.md           # 安全说明
├── TEST_PLAN.md          # 测试计划
├── LICENSE               # MIT License
└── .gitignore
```

## 致谢

Fuxi 受到公开 agent loop 和 workflow discipline 相关工作的启发, 尤其是 alchaincyf 的 Loop Engineering Orange Book。

它也吸收了公开讨论中关于 agent 行为、提示词稳健性、工具使用纪律和多 agent 交接设计的一般经验。本仓库不包含复制的私有系统提示词。

更多说明见 `ACKNOWLEDGEMENTS.md`。

## 许可证

MIT License. 见 `LICENSE`。