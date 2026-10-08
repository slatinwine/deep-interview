# deep-interview · 深度采访

把 AI 变成记者。围绕一个主题采访**你本人**：从兴趣爱好破冰，逐层深入到经历、观点与价值观，最后整理成一篇一问一答的采访长文——用于整理思路，或给自己留一份人物侧写。

## 它是怎么采访的

漏斗五层，层层收窄：

| 层 | 问数 | 聊什么 |
|---|---|---|
| 破冰 | 1–3 | 兴趣爱好、最近在忙什么——让受访者进入表达状态 |
| 铺垫 | 2–4 | 从兴趣自然过渡到主题：怎么入的坑、什么契机 |
| 深入 | 4–8 | 观点与方法 → 具体经历和故事 → 踩过的坑 |
| 内核 | 2–4 | 动机与价值观：为什么重要、想成为什么样的人 |
| 收尾 | 1–2 | 展望、"有什么我没问到但你想说的" |

记者式提问规则写在 SKILL.md 里：每轮只问一个开放式问题、引用你的原话追问、抽象回答要具体例子（"最难的一次是什么时候？"）、不审问、跑题先接再拉、尊重拒答。

## 三个防御性设计

和"让 AI 随便问我十个问题"的区别在这里：

1. **原话落盘**。每轮问答后立即把你的原话追加进 `interviews/日期-主题-transcript.md`。长对话会被上下文压缩摘要丢掉细节——成稿必须基于底稿文件，而不是模型记忆。
2. **忠实性红线**。成稿只把口语理顺成书面语：不添加你没说过的内容、不代你拔高观点、不虚构细节。侧写手记里"事实"与"推测"强制分开，推测必须标明是推测。
3. **深问不给选项**。开放式问题直接用文本问；结构化选择工具只用于开场设定和"先挖 A 还是 B"这类方向选择——选项会框住回答，而采访的价值恰恰在选项之外。

## 安装

**方式一：SkillHub（国内源，推荐）**

```bash
# 需先安装 SkillHub CLI：curl -fsSL https://skillhub-1388575217.cos.ap-guangzhou.myqcloud.com/install/install.sh | bash
skillhub install deep-interview --namespace user_79ac54a9 --dir ~/.agents/skills/
```

**方式二：GitHub**

```bash
git clone https://github.com/slatinwine/deep-interview.git
```

把 `deep-interview/` 目录放进你所用 Agent 的 skills 目录：

| Agent | skills 目录 |
|---|---|
| ZCode | `~/.agents/skills/` 或 `~/.zcode/skills/` |
| Claude Code | `~/.claude/skills/` |
| Codex | `~/.codex/skills/` 或项目下 `.agents/skills/` |
| Cursor | `~/.cursor/skills/` |
| Gemini CLI | `~/.gemini/skills/` |

## 用法

新会话里说一句就触发：

- "采访我一下，主题是我做 XX 这条线的思路"
- "给我做个侧写吧，聊聊我这个人"
- "帮我整理下我对 XX 的看法，采访形式"

开场会确认三件事：**主题**、**目的**（整理思路 / 人物侧写 / 两者）、**深度**（速聊 8–10 问 / 深谈 15–20 问）。成稿输出到 `interviews/日期-主题-采访.md`，底稿原话保留不动。

## 目录结构

```
deep-interview/
├── SKILL.md                  # 采访流程、提问规则、成稿规范
└── references/
    └── question-bank.md      # 分主题问题库：技术 / 创作 / 事业项目 / 人生成长 / 观点理念
```

## 实测

首场实测对一位独立开发者做了 17 问深谈——从"在看素书"破冰，到"怎么防止 AI 暴走、毁灭人类"收尾，产出约 4000 字成稿 + 采访手记。实测中暴露的 transcript 追加陷阱（Edit 误将追加写成替换导致静默丢答案）已经以正确写法固化进 SKILL.md。

**[→ 阅读首场采访成稿《从哭成狗到拔电源——一个独立开发者的 AI 九年》](https://slatinwine.github.io/deep-interview/)**

## License

MIT
