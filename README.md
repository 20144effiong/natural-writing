# Natural Anti-Defensive Writing

让 AI 的中英文表达更自然、直接，减少套话、机械句式和预先辩解，同时保留作者声音与证据准确性。

A compact Agent Skill for natural, direct writing: reduce formulaic phrasing and unnecessary defensive caveats while preserving voice, meaning, and evidence.

## 内容

这个技能将 [blader/humanizer](https://github.com/blader/humanizer) 与 [Kiterlin/anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing) 合并、去重并精简为 9 条规则，适用于日常回答、教学解释、进度说明、技术文档和科研写作。

- 先讲要点，再给理解和判断所需的理由。
- 删除无信息的开场、重复总结、空泛拔高和假想反驳。
- 保留有作用的对比、自然段落、作者语气和专业术语。
- 必要限定说清一次，负结果、统计不确定性和实质局限照实保留。
- 改稿不改变事实、条件、归因、完成状态、代码或数据。
- 默认直接交付成稿，只有用户要求时提供审校说明。

完整规则见 [SKILL.md](SKILL.md)。该技能改善文字表达，不用于判断作者身份或承诺通过 AI 检测。

## 安装到 Codex

将仓库放入用户技能目录，让 `SKILL.md` 位于 `~/.agents/skills/natural-anti-defensive-writing/SKILL.md`。

Windows PowerShell:

```powershell
git clone https://github.com/20144effiong/natural-anti-defensive-writing.git "$env:USERPROFILE/.agents/skills/natural-anti-defensive-writing"
```

macOS / Linux:

```bash
git clone https://github.com/20144effiong/natural-anti-defensive-writing.git ~/.agents/skills/natural-anti-defensive-writing
```

如果目标目录已经存在，先检查现有内容，避免覆盖自己的修改。安装后可显式调用 `$natural-anti-defensive-writing`。若技能列表尚未刷新，重新启动 Codex。

如需作为所有本地 Codex 工作区的默认表达规则，可在 Codex 主目录的 `AGENTS.md` 中添加下面这段，并将占位路径替换为实际安装位置:

```text
所有对话默认应用 natural-anti-defensive-writing。
本会话首次应用时读取 <技能安装目录>/SKILL.md，之后沿用。
保留具体任务要求的语言、篇幅、文体、格式和专业约束。
```

已有会话需重新加载指令。项目中的更具体指令仍可能覆盖全局默认。该本地安装方式不会自动同步到普通 ChatGPT 手机聊天或独立云环境。

## 使用示例

```text
用 $natural-anti-defensive-writing 修改下面这段文字。
保留事实和作者语气，直接给出修改后的正文。
```

示例原句:

> 需要指出的是，我们仅在两个数据集上进行了初步尝试，因此该结果可能或许能够在一定程度上提示方法具有潜力。

若已知事实只有“在两个数据集上评估了方法”，可以写为:

> 我们在两个数据集上评估了该方法。

若“初步”描述真实研究阶段，则应保留。技能不要求删除所有限定词，也不把语气更肯定当作证据更充分。

## 上游来源与改动

| 来源 | 固定提交 | 保留的重点 |
|---|---|---|
| [blader/humanizer](https://github.com/blader/humanizer) | `0ef9fe5bc3572734fd3ae6c448fe00a30cd5dcf0` | 模板化结构、空话、作者声音与信息保真 |
| [Kiterlin/anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing) | `f516147d017a3fe43ae99192cb89d8261b0c8679` | 直接论述、必要限定、证据与负结果处理 |

本仓库是上述项目的精简改编版。合并了重复语义和中英文重复规则，省略长例子及默认展示多轮改稿的流程，将机械禁词和标点禁令改为结合语境判断，并补充日常对话与教学的适用说明。

固定版本、下载地址和归档校验值记录在 [SOURCES.json](SOURCES.json)。技能格式经过本地校验，未做模型间效果评测。

## 许可证

[MIT](LICENSE)。保留 Siqi Chen、Kiterlin 的上游版权声明，合并改编由 `20144effiong` 发布。
