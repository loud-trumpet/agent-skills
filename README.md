# agent-skills

The skills behind the writing on [Loud Trumpet](https://www.loud-trumpet.com).

These are not examples. They are the files in use, copied from the repo the blog
is written in, and they are what the model reads before it drafts or reviews
anything published there.

They are here because the posts say AI is involved in writing them, and a claim
like that is worth less than the instructions behind it. Read them and you know
what the model was told. What they cannot show you is whether the rules were
followed, which is covered in
[Who is writing this](https://www.loud-trumpet.com/who-is-writing-this/).

## The skills

| Skill | What it does |
| --- | --- |
| [`write-blog-post`](write-blog-post/SKILL.md) | Interview first, then draft. Holds the voice definition, the evidence discipline and the file conventions. |
| [`review-draft`](review-draft/SKILL.md) | Audits a draft for overclaiming, contradictions, caveats bolted onto claims they contradict, and rigged comparisons. |
| [`address-notes`](address-notes/SKILL.md) | Finds the notes left inline in a draft, in square brackets, and works through them. |

The rule that does the most work is in `write-blog-post`:

> **Never fill a gap with a plausible invention.** If an answer does not arrive,
> the section does not get written.

## Using them

These are [Claude Code skills](https://docs.claude.com/en/docs/claude-code/skills).
Each directory holds a `SKILL.md` with frontmatter describing when it applies.
Drop a directory into `.claude/skills/` in your own project and it becomes
available there.

They are written for one blog and refer to its conventions throughout, so they
are more likely to be worth reading than running. The parts that generalize are
the interview, the evidence rules and the review checklist. The parts that do
not are every path and frontmatter field.

## License

MIT. See [LICENSE](LICENSE).
