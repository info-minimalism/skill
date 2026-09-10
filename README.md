# Info-Minimalism Evaluation Skill

An AI-agent skill for cutting wasted attention in social posts, news, educational content, threads, and channels. Entertainment content is outside the method.

**Version 1.0.0 — stable.**

It preserves the expressed meaning, proposes a lower-cost rendering, and identifies burdens such as repetition, delayed payload, or artificial fragmentation. It does not fact-check, infer creator effort, or award an overall score. It supports a publisher's own commitment to check every new publication, not certification by an outside authority.

## Install

Install the skill into an agent that supports skills, such as [Codex](https://learn.chatgpt.com/docs/build-skills), [Claude Code](https://code.claude.com/docs/en/skills), or [Gemini CLI](https://geminicli.com/docs/cli/using-agent-skills/). Ask:

> Install the Info-Minimalism evaluation skill from https://github.com/info-minimalism/skill for use in my future conversations. Confirm when it is available and tell me if I need to restart the agent.

Follow your agent's setup and permission requests. Install the whole package, including `references/` and `scripts/`, not just `SKILL.md`.

## Evaluate

Paste a post or provide its link. For a thread, provide the whole thread or its link. For a channel, ask the agent to check a recent sample, such as the last twenty informational posts, and identify what it checked.

> Use the Info-Minimalism evaluation skill to check this content for wasted attention. I read it **[in my feed / as a notification / after finding it through search]**. Keep the result brief and show what can be cut or reorganized without losing meaning.

## Publisher feedback

Send this yourself:

> This content wasted my attention. Please check it against the attention contract with the Info-Minimalism evaluation skill: https://github.com/info-minimalism/skill

Or ask your agent to write the feedback:

> Use the Info-Minimalism evaluation skill to check this content. Then draft a short, polite message to the publisher with one clear attention problem and one practical change. Include the skill link. Show me the draft before sending.

These are the installation, evaluation, and feedback prompts from Part II of *Info-Minimalism: The Discipline of Meaning in an Age of Infinite Content*.

For a headline that withholds the answer, the reader can send:

> The headline withholds the main point. Please state it directly and follow the Info-Minimalism Standard: https://github.com/info-minimalism/skill

Use this when the content actually withholds the main point. A skill-issued attention finding needs accessible evidence, not a guess about a headline or the publisher's intent. Review any agent-written feedback before sending it.

## Other agent tasks from the book

These requests use the agent's general capabilities, not additional evaluation-skill modes.

Get the answer behind a teaser:

> Find the answer this headline is withholding. Use the full content or an accessible primary source. Give me the answer briefly and link the source. If you cannot read the material, say so rather than guessing from the headline.

The agent needs legitimate access to source material; this request does not unlock restricted content or guarantee a correct summary.

Exclude a source from your own briefings:

> Avoid this source in my briefings when an adequate alternative is available. Tell me when it is the only relevant primary source.

This is a personal source preference, not a request to alter search rankings or other people's AI citations. Repeat it when needed if the agent does not retain preferences.

## For creators

Revise a draft, as in Chapter 9:

> Use the Info-Minimalism evaluation skill to revise this draft for **[audience]**, who will read it **[where]**. Remove avoidable attention cost while preserving meaning and natural language. Show the revision first, followed by any changes I need to check.

Then, if useful, request a separate source comparison as in Chapter 12. This is a general agent task, not part of the attention-cost evaluation or a truth certificate:

> Compare this revision with the original draft and the source material I provide. Flag any changed claim, number, attribution, uncertainty, or condition. Do not add facts or publish anything.

Review the changes before publishing. The source-comparison request does not expand the evaluation skill's scope.

## Publisher self-certification

[![Info-Minimalist badge](assets/badge/info-minimalist-badge-color.svg)](assets/badge/README.md)

[Download the badge and mark](assets/badge/README.md) in SVG or PNG, with color, black, and white versions. Link the badge on your site or profile to your publishing declaration.

The checkmark means: “We check every new in-scope post before publishing, using the latest published Standard, and resolve its supported findings.”

Read [the short procedure and declaration](references/publisher-self-certification.md). No outside permission, registry, or renewal calendar is required. Readers can question the claim through ordinary feedback. A clean sample is not a substitute for checking future posts.

To check a final draft:

> Use the Info-Minimalism evaluation skill to check this final draft before publication. Check which Standard version is current, include any relevant earlier posts, and tell me what needs resolving before it meets the requirements. Do not publish anything.

The publisher makes the declaration; the agent checks the content and helps keep the supporting evidence. An evaluation request does not authorize posting or adding a checkmark.

## Version and records

The [Standard](references/standard-v1.0.0.md), [version manifest](release.json), and [result schema](references/evaluation-result.schema.json) travel with the skill. Evaluations retain the version actually used. Version 1.0 adds P1 qualification and the publisher's ongoing commitment; it does not re-label old evaluations as certified.

Brief reader answers are the default. Full structured records are available when useful or requested. Counts are proxies, not a universal measure of mental effort.

For structured records, see [validation](references/structured-results.md).

## Manifesto and reuse

Read the founding [Info-Minimalism Manifesto](https://github.com/info-minimalism/manifesto).

The skill instructions and code use the MIT License; see [the exact scope and terms](LICENSE.md). The Standard and method documentation are not covered by this grant. Badge artwork keeps its separate [display permission](assets/badge/README.md).
