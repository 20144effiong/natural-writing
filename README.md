# Natural Writing

A concise Agent Skill for clear, natural prose that preserves the writer's voice, meaning, and evidence. Use it for conversations, teaching, progress updates, technical documents, and research writing.

The instructions are in English. Responses follow the language requested by the user, including Chinese.

## What it does

- Leads with the answer and keeps the reasoning needed to understand it.
- Removes filler, formulaic phrasing, inflated claims, and repeated caveats.
- Preserves useful contrast, paragraph flow, technical meaning, and personal voice.
- States uncertainty precisely and retains material limitations and negative results.
- Keeps facts, conditions, attribution, completion status, code, and data intact.
- Returns finished prose by default, with an editing report only when requested.

The complete workflow contains nine rules in [SKILL.md](SKILL.md). It improves expression without classifying authorship or promising detector results.

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

If the destination already exists, inspect it before making changes. Invoke the skill explicitly with `$natural-writing`. Restart Codex if the skill list has not refreshed.

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

The adaptation combines overlapping rules, removes duplicated language versions and lengthy examples, replaces mechanical word bans with contextual judgment, and uses a single final-output workflow. The skill format has been validated locally. No comparative model evaluation has been performed.

## License

[MIT](LICENSE). Original copyright notices are retained.
