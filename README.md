# Natural Writing

Two complementary Agent Skills for natural prose and connected explanations. Natural Writing preserves the writer's voice, meaning, and evidence. Teach Without Gaps explains concepts and justifies the steps needed to understand an answer.

The instructions are in English. Responses follow the language requested by the user, including Chinese.

## Included skills

| Skill | Entry point | Purpose |
| --- | --- | --- |
| Natural Writing | [SKILL.md](SKILL.md) | Clear, natural prose with precise claims and preserved meaning. |
| Teach Without Gaps | [skills/teach-without-gaps/SKILL.md](skills/teach-without-gaps/SKILL.md) | Explanations, derivations, code walkthroughs, confusion repair, and teaching-material revisions without skipped steps. |

Teach Without Gaps is self-contained. Its defaults cover knowledge questions across conversations, including mathematics, AI, programming, algorithms, and English grammar. It defines unfamiliar concepts before using them, supplies the justification for important transitions, and changes the explanation when a learner remains confused. It also covers slides and handouts: preserve the template, explain sentence transformations and usage conditions, and keep visible slides readable.

The two skills can be used together. The teaching skill retains a Simplified Chinese default for its author's use, while honoring any requested language. Its instructions and interface metadata are in English. Factual lookups and requests for answers only remain brief.

Both skills default to connected paragraphs. Their internal rules are not response templates. Lists are reserved for explicit requests or concrete procedures and comparisons that are substantially easier to follow in that format. Teaching still preserves necessary reasoning and derivations.

## What Natural Writing does

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

## Install Teach Without Gaps

After cloning this repository using the instructions above, copy the teaching skill into a sibling directory so its entrypoint is at `~/.agents/skills/teach-without-gaps/SKILL.md`. Copy the whole folder, including its interface metadata and icon.

First check that the destination does not already exist. If it does, inspect the existing installation before updating it.

Windows PowerShell:

```powershell
$teachingSource = "$env:USERPROFILE/.agents/skills/natural-writing/skills/teach-without-gaps"
$teachingTarget = "$env:USERPROFILE/.agents/skills/teach-without-gaps"
if (Test-Path $teachingTarget) { throw "Destination already exists. Inspect it before updating." }
Copy-Item -LiteralPath $teachingSource -Destination $teachingTarget -Recurse
```

macOS / Linux:

```bash
teaching_source="$HOME/.agents/skills/natural-writing/skills/teach-without-gaps"
teaching_target="$HOME/.agents/skills/teach-without-gaps"
if [ -e "$teaching_target" ]; then
  echo "Destination already exists. Inspect it before updating."
else
  cp -R "$teaching_source" "$teaching_target"
fi
```

Invoke it with `$teach-without-gaps` in Codex or select it with an `@` mention in ChatGPT where the skill is installed. The metadata allows automatic matching. A GitHub copy alone does not install the skill into a ChatGPT account.

For a default across local Codex workspaces, add the following to the same global `AGENTS.md`, replacing the placeholder with the actual teaching-skill path:

```text
Apply teach-without-gaps by default to knowledge questions, explanations, exercises,
follow-up confusion, and teaching materials in all conversations.
Read <teaching-skill-installation-directory>/SKILL.md when first applying it in a session.
Honor the user's requested language, depth, length, and answers-only requests.
Use it with natural-writing when both apply.
```

Skill descriptions and local instructions establish defaults. Loading remains host-dependent, and more specific user or project instructions still apply.

## Teaching example requests

```text
Use $teach-without-gaps to explain why the number of free variables equals
the dimension of the null space. Explain the missing connection, not just the theorem name.
```

```text
Use $teach-without-gaps to revise these English grammar slides.
Keep the template and explain each sentence transformation, its meaning,
and the conditions under which the structure is used.
```

## Natural Writing example request

```text
Use $natural-writing to revise the following passage.
Preserve its facts and the writer's voice. Return only the finished text.
```

For a source that establishes only that a method was evaluated on two datasets:

> It is worth noting that we only conducted an evaluation of this method on two datasets.

A direct revision is:

> We evaluated the method on two datasets.

Retain sample scope or preliminary status when it affects interpretation. Clearer wording must not make the evidence sound stronger than it is.

## Natural Writing sources and adaptation

Adapted from MIT-licensed work by **Siqi Chen** and **Kiterlin**, with the merged adaptation maintained by **20144effiong**.

[SOURCES.json](SOURCES.json) records the original repository IDs, owners, pinned commits, and archive checksums. The API links identify the repositories independently of their current names.

The adaptation retains the natural-writing rules and the full set of distinct revision rules in the pinned Kiterlin source. Repeated Chinese and English versions are consolidated into English instructions, including English explanations of the Chinese-language guidance. The examples are retained with an explicit requirement to verify their facts before using them. Source project names are omitted from the skill's prose. Copyright notices and revision provenance remain in LICENSE and SOURCES.json.

The coverage review compares instructions and examples, not installation scripts, issue templates, or repository artwork. A structural check and targeted editing checks are described below. No comparative model evaluation has been performed.

## Natural Writing rule coverage

The expanded workflow covers the following distinct rule groups from the pinned source revision in SOURCES.json. This is semantic coverage of the rules, conditions, procedures, and examples, with duplicate language versions consolidated.

| Rule group | Location in SKILL.md |
| --- | --- |
| Direct claims and a calm authorial voice | Opening guidance and Core Writing Rules |
| Accuracy, ethics, law, safety, and methodological limits | Preserve Necessary Precision |
| Five tests for whether a limitation matters | Preserve Necessary Precision |
| Placement of limitations and sentence-level exceptions | Preserve Necessary Precision |
| Ten checks for unnecessary caveats and framing | Revision Checklist |
| Sentence functions and revision guidance | Rewrite Procedure |
| Positive scope, precise uncertainty, and paragraph structure | Rewrite Procedure and Writing Principles |
| Technical purpose, parameters, prerequisites, and missing conditions | Technical Plans and SOPs |
| Necessary prohibitions, non-interchangeability, and exact operations | Technical Plans and SOPs |
| Preferred and discouraged sentence patterns | Preferred Patterns and Discouraged Patterns |
| Five illustrative before-and-after revisions | Examples |
| Language choice and local editing scope | Opening guidance and Research-Specific Guidance |
| Main contribution and supporting contributions | Main Argument |
| Unfavorable metrics and concrete tradeoffs | Metrics and Claims |
| Four experimental questions and missing ablations | The Role of Each Experiment |
| Handling unfavorable results | Procedure for Unfavorable Results |
| Submission checks and reviewer/manuscript distinctions | Before Submission and Review Comments and Manuscript Text |
| Chinese modesty and English hedging without inflated claims | Modesty in Chinese-Language Writing and English Patterns |
| Examples as phrasing guidance, never a source of facts | Examples and Using the Examples |
| Final output without unnecessary review artifacts | Core Writing Rules and Final Pass |

## Validation

Teach Without Gaps passed frontmatter validation and targeted checks using vector-space dimension, the free-variable basis argument, array bounds, and an answers-only vocabulary request. Its cross-conversation and teaching-material defaults are explicit in its entrypoint. These checks are limited examples, not a benchmark.

The skill is checked for valid frontmatter, English-only instructions, complete referenced files, and preservation of its nine original core rules. Targeted editing checks exercise numeric tradeoffs, missing ablation evidence, Chinese SOP conditions and prohibitions, observational uncertainty, and prevention of invented facts. These checks are limited examples, not a benchmark or a guarantee of model behavior.

## License

[MIT](LICENSE). Original copyright notices are retained.
