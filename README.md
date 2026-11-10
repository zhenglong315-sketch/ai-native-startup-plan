# AI 原生创业方案 Skill（ai-native-startup-plan）

一个 AI 技能（Agent Skill）：用 5 批问卷引导你，按「创意 → MVP → 上线 → 规模化」四阶段框架，生成一份完整的 AI 原生创业方案。

适用于 **Claude（桌面端 / 网页版）、Claude Code、Codex、WorkBuddy** 等支持 `SKILL.md` 格式的 AI 工具。

> An agent skill that walks founders through a 5-batch questionnaire and produces a four-stage (Idea → MVP → Launch → Scale) AI-native startup plan, based on *The Founder's Playbook: Building an AI-Native Startup*. Content is in Chinese.

## 它会做什么

1. **分批问卷**：基本信息 → 创意 → MVP → 上线 → 规模化，每批一次问完。答"不知道"也可以，会被记为待验证假设。
2. **每批回答后**：给出本批小结、阶段门槛判定（✅ / ⚠️ / ❌）、针对你项目的反方提示，以及可选的补充项。
3. **生成方案**：
   - 门槛状态总表和最大的三个风险
   - 每个阶段的门槛自查、陷阱自查、行动计划
   - **已填入你项目信息、可直接使用的提示词**（每个阶段 3–5 个）
   - 待验证假设清单
   - 本周就能开始的三件事
4. **不卡人**：门槛没过时，在方案里标 ⚠️ 写明风险，照常写完四个阶段。说「直接生成」可以随时提前结束。
5. **不编造**：没有的数据标【待补】并附上验证方法；AI 的推断标「💡 AI 推断，待验证」。

完整效果见示例：[examples/MeetTask_AI原生创业方案.md](examples/MeetTask_AI原生创业方案.md)。该示例由模拟用户生成，项目和数据均为虚构。

## 安装

技能本体在仓库的 [`ai-native-startup-plan/`](ai-native-startup-plan/) 文件夹里。**安装时整个文件夹一起放，不要改文件夹名。**

### Claude Code

```bash
git clone https://github.com/zhenglong315-sketch/ai-native-startup-plan.git
cp -r ai-native-startup-plan/ai-native-startup-plan ~/.claude/skills/
```

### Codex

在 Codex 中运行：

```
$skill-installer https://github.com/zhenglong315-sketch/ai-native-startup-plan/tree/main/ai-native-startup-plan
```

也可以手动把文件夹复制到 `~/.agents/skills/`（旧版本用 `~/.codex/skills/`）。装完后重启 Codex。

### WorkBuddy

两种方式任选：
- 在技能面板通过 GitHub 地址安装
- 把文件夹复制到 `~/.workbuddy/skills/` 后重启

### Claude 桌面端 / 网页版

1. 到 [Releases](https://github.com/zhenglong315-sketch/ai-native-startup-plan/releases) 下载 `ai-native-startup-plan.zip`
2. 打开 设置 → 功能（Capabilities）→ 技能（Skills），上传 zip

> 各工具的菜单名称和路径可能随版本变化，以实际界面为准。Windows 上的 `~` 指 `C:\Users\<用户名>`。

## 使用

新开一个对话，说下面任意一句：

- 「帮我做一份 AI 原生创业方案」
- 「我有个产品想法：……，帮我从创意到规模化规划一下」

没有自动触发的话，直接点名：「用 ai-native-startup-plan 技能帮我做方案」。

## 文件结构

```
ai-native-startup-plan/
├── SKILL.md                    # 流程、判定规则、写法规则
└── references/
    ├── questionnaires.md       # 5 批问卷
    ├── methodology.md          # 四阶段方法论（目标、门槛、陷阱、步骤）
    ├── prompts.md              # 提示词模板 T1–T28
    └── plan-template.md        # 方案输出结构
```

## 来源与版权说明

- 方法论框架、`references/methodology.md` 和 `references/prompts.md` 的内容，提炼自《创始人实战手册：打造 AI 原生初创企业》（*The Founder's Playbook: Building an AI-Native Startup*，Claude 出品），中文译者董浩宇博士。这部分内容的权利归原作者及译者所有，**不在本仓库许可证的授权范围内**。
- 本仓库作者原创的部分包括问卷设计、阶段门槛判定规则、方案输出模板和技能流程，以 [CC BY 4.0](LICENSE) 许可发布。
- 如果权利人对本仓库内容有异议，请提交 Issue，我会及时处理。

## 许可证

原创部分采用 [Creative Commons Attribution 4.0 International（CC BY 4.0）](LICENSE)。
