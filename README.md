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

## Installing them

These are [Claude Code skills](https://docs.claude.com/en/docs/claude-code/skills).
A skill is a directory holding a `SKILL.md`, whose frontmatter says when it
applies. Copy the directories you want into either place:

```bash
# available in one project
mkdir -p .claude/skills
cp -R write-blog-post review-draft address-notes .claude/skills/

# available everywhere
cp -R write-blog-post review-draft address-notes ~/.claude/skills/
```

Start a new session afterward. Run `/write-blog-post` to invoke one by name, or
describe the task and let the model match the description itself.

## How they fit together

They are three stages of one workflow, and they are meant to run in order.

1. **`write-blog-post`** is the entry point. It interviews you before it drafts
   anything, one question at a time, and refuses to invent an example when an
   answer does not arrive. Most of the work happens here.
2. **`address-notes`** is for the review round. Read the draft, leave notes
   inline in square brackets wherever something is wrong, then run this. It
   finds them, sorts the ones that change a fact from the ones that change
   wording, and tells you which it disagreed with.
3. **`review-draft`** runs last, before anything is published. It audits for
   overclaiming, internal contradictions, caveats bolted onto the claims they
   contradict, and comparisons rigged in their own favor.

`write-blog-post` tells the model to run `review-draft` at the end, and
`address-notes` defers to `write-blog-post` on evidence rules. Taking only one
of the three works, but the handoffs will refer to something you do not have.

## Adapting them

They were written for one blog and name its conventions throughout. Read them
before you run them, and expect to change:

- **Paths.** `posts/`, `images/`, `social/` and `_ideas/series/` are this repo's
  layout, and they appear in all three skills.
- **Frontmatter.** The field list in `write-blog-post` is what this site's
  publisher accepts, including an `audience` field that never reaches the site.
- **The voice.** The voice section describes how one person writes, down to the
  rule against em dashes and the ban on specific words. Replacing it with a
  description of your own writing is most of the work of making these yours.
- **Publishing.** The last section of `write-blog-post` refers to commands that
  exist only in the blog repo.

What survives the adaptation is the shape: interview before drafting, label
which claims are lived and which are conviction, state the limits before a
reader can raise them, and never fill a gap with something plausible.

## License

MIT. See [LICENSE](LICENSE).
