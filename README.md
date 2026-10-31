# Natural Writing

An Agent Skill for clear, natural prose that preserves the writer's voice, meaning, and evidence. Use it for conversations, teaching, progress updates, technical documents, and research writing.

The instructions are in English. Responses follow the language requested by the user, including Chinese.

## What it does

- Leads with the answer and keeps the reasoning needed to understand it.
- Removes filler, formulaic phrasing, inflated claims, and repeated caveats.
- Preserves useful contrast, paragraph flow, technical meaning, and personal voice.
- States uncertainty precisely and retains material limitations and negative results.
- Keeps facts, conditions, attribution, completion status, code, and data intact.
- Returns finished prose by default, with an editing report only when requested.

[SKILL.md](SKILL.md) contains nine core writing rules plus detailed revision procedures, technical-writing guidance, research checks, and examples. It improves expression without classifying authorship or promising detector results.

## Install in Codex

Place this repository in your user skills directory so that the entrypoint is at `~/.agents/skills/natural-writing/SKILL.md`.

Windows PowerShell:

```powershell
git clone https://github.com/20144effiong/natural-writing.git "$env:USERPROFILE/.agents/skills/natural-writing"
```

macOS / Linux:

```bash
git clone https://github.com/20144effiong/natural-writing.git ~/.agents/skills/natural-writing
```

If the destination already exists, inspect it before making changes. Invoke the skill explicitly with `$natural-writing`. Refresh the skill list or begin a new session if the update is not yet visible.

To make it the default writing style across local workspaces, add this to `AGENTS.md` in your Codex home directory, replacing the placeholder with the actual installation path:

```text
Apply natural-writing by default in all conversations.
Read <skill-installation-directory>/SKILL.md when first applying it in a session.
Preserve the user's requested language, length, register, format, and task-specific requirements.
```

Existing sessions need to reload their instructions. More specific project instructions can override global defaults. Local installation does not automatically configure ordinary ChatGPT mobile chats or separate cloud environments.

## Example request

```text
Use $natural-writing to revise the following passage.
Preserve its facts and the writer's voice. Return only the finished text.
```

For a source that establishes only that a method was evaluated on two datasets:

> It is worth noting that we only conducted an evaluation of this method on two datasets.

A direct revision is:

> We evaluated the method on two datasets.

Retain sample scope or preliminary status when it affects interpretation. Clearer wording must not make the evidence sound stronger than it is.

## Sources and adaptation

Adapted from MIT-licensed work by **Siqi Chen** and **Kiterlin**, with the merged adaptation maintained by **20144effiong**.

[SOURCES.json](SOURCES.json) records the original repository IDs, owners, pinned commits, and archive checksums. The API links identify the repositories independently of their current names.

The adaptation retains the natural-writing rules and the full set of distinct revision rules in the pinned Kiterlin source. Repeated Chinese and English versions are consolidated into English instructions, including English explanations of the Chinese-language guidance. The examples are retained with an explicit requirement to verify their facts before using them. Source project names are omitted from the skill's prose. Copyright notices and revision provenance remain in LICENSE and SOURCES.json.

The coverage review compares instructions and examples, not installation scripts, issue templates, or repository artwork. A structural check and targeted editing checks are described below. No comparative model evaluation has been performed.

## Rule coverage

The expanded workflow covers the following distinct rule groups from the pinned source revision in SOURCES.json. This is semantic coverage of the rules, conditions, procedures, and examples, with duplicate language versions consolidated.

| Rule group | Location in SKILL.md |
| --- | --- |
| Direct claims and a calm authorial voice | Opening guidance and Core Writing Rules |
| Accuracy, ethics, law, safety, and methodological limits | Preserve Necessary Precision |
| Five tests for whether a limitation matters | Preserve Necessary Precision |
| Placement of limitations and sentence-level exceptions | Preserve Necessary Precision |
| Ten checks for unnecessary caveats and framing | Revision Checklist |
| Six-way sentence classification and five-step revision | Rewrite Procedure |
| Positive scope, precise uncertainty, and paragraph structure | Rewrite Procedure and Writing Principles |
| Technical purpose, parameters, prerequisites, and missing conditions | Technical Plans and SOPs |
| Necessary prohibitions, non-interchangeability, and exact operations | Technical Plans and SOPs |
| Preferred and discouraged sentence patterns | Preferred Patterns and Discouraged Patterns |
| Five illustrative before-and-after revisions | Examples |
| Language choice and local editing scope | Opening guidance and Research-Specific Guidance |
| Main contribution and supporting contributions | Main Argument |
| Unfavorable metrics and concrete tradeoffs | Metrics and Claims |
| Four experimental questions and missing ablations | The Role of Each Experiment |
| Five-step handling of unfavorable results | Procedure for Unfavorable Results |
| Submission checks and reviewer/manuscript distinctions | Before Submission and Review Comments and Manuscript Text |
| Chinese modesty and English hedging without inflated claims | Modesty in Chinese-Language Writing and English Patterns |
| Examples as phrasing guidance, never a source of facts | Examples and Using the Examples |
| Final output without unnecessary review artifacts | Core Writing Rules and Final Pass |

## Validation

The skill is checked for valid frontmatter, English-only instructions, complete referenced files, and preservation of its nine original core rules. Targeted editing checks exercise numeric tradeoffs, missing ablation evidence, Chinese SOP conditions and prohibitions, observational uncertainty, and prevention of invented facts. These checks are limited examples, not a benchmark or a guarantee of model behavior.

## License

[MIT](LICENSE). Original copyright notices are retained.
