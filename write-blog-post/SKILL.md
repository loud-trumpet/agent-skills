---
name: write-blog-post
description: Draft or revise a post for the Loud Trumpet blog in Ryan's voice, with the repo's file, image and SEO conventions. Use for any post, standalone or part of a series.
---

# Writing a post

## Interview before drafting

The series' credibility comes from lived evidence, and the evidence lives with
Ryan rather than in this repo. A scene, a number, a real example, an outcome, a
mistake: none of these can be inferred from the plan or the earlier posts, and
inventing one destroys the thing the whole blog is trading on.

So the first move on any new post is an interview, not a draft. Ask, then write.
Do not write a draft with gaps in it and ask afterward, because the answers
reshape the argument around them and the draft gets rewritten anyway.

**What the interview has to get.** At minimum, every one of these:

- **The opening scene.** A specific failure or moment, with a number attached.
  Ask what actually went wrong, how long it stood, and how it was found. This is
  the hardest thing to invent and the most important thing to get.
- **The concrete examples.** Two or three, with enough detail to be checkable:
  what the thing was, what it was built from, how many places it was used. An
  abstract example reads as an abstract post.
- **The numbers.** How long, how many, how much faster. A claim with a number is
  a report; the same claim without one is an opinion.
- **The mistake.** What was built wrong, or too early, or too late. A post with
  one of these in it is believed; a post without one reads as a sales pitch.
- **The limits.** What the experience does not establish. Ask directly: what
  would you not be willing to claim from this?
- **The evidence line.** For each section, lived or conviction. Ask rather than
  guess, and put the answer in the text.
- **The audience.** Who is this for, and what are they assumed to already know?
  Ask for a sentence, not a category. "Technical" and "non-technical" are too
  coarse to decide anything: the real question is per-term, and a label gets it
  wrong in both directions. It cuts a term that carries the argument, and it
  keeps a term that quietly narrows the post. The answer goes in the
  `audience` frontmatter field and stays there, because it is obvious while
  you are talking and gone a week later.

**When a series plan exists, its "what this post needs before drafting" list is
the interview agenda.** Work straight down it. Anything still open in the plan's
"open questions" that touches this post gets asked too.

**How to ask: one question at a time.** Ask a single question, wait for the
answer, then ask the next one. A numbered list of ten questions gets a list of
ten short answers, and short answers are exactly what this interview cannot use.
One question at a time gets a story, and the story is where the scene, the
number and the mistake are hiding.

It also lets each question be shaped by the last answer, which is most of the
value. The follow-up is usually more productive than the question that prompted
it: ask how it was noticed, what it cost, what was tried first, who pushed back.
Keep pulling on an answer while it is still producing detail, and move on when
it stops.

**Expect prose, not a selection.** Almost nothing in this interview is a choice
between options, so `AskUserQuestion` is the wrong instrument for it: recall has
no options to offer, and offering some invites an answer shaped by the guesses
rather than by what happened. Ask in plain text and say that a paragraph, a
tangent or "that never came up" are all fine answers. Reserve `AskUserQuestion`
for the few places where the answer really is a decision between known
alternatives, such as a title, or whether to name a company.

**Then confirm before writing.** Play the material back in a few lines: here is
the scene, here is the argument it supports, here is what I will say the
evidence does not cover. A wrong reading caught in three lines is cheaper than a
wrong reading caught in a finished draft.

**Never fill a gap with a plausible invention.** If an answer does not arrive,
the section does not get written. A placeholder marked as a placeholder is
acceptable in an intermediate state; a fabricated example is not, at any stage,
including a draft nobody has agreed to publish yet.

## Voice

Ryan's voice is plain, concrete, and unhedged. It earns authority by being
specific and by admitting what it can't prove, never by sounding confident.

**Open on a scene, not a thesis.** The strongest opening is a specific failure
with a number attached. One post opens "For about a month, one of our buttons had
white text on a white background." No setup, no framing, no "in this post I'll
argue". The argument arrives after the reader is already in it.

**Short declarative sentences.** Fragments are fine when deliberate: "Not
defaulted. Not documented as 'usually this one.' The parameter wasn't there."

**One idea per paragraph, and paragraphs stay short.** Two to four sentences.

**Precision instead of hedging.** Don't reach for "maybe", "might", "probably",
"sometimes". Either the claim is true as stated, or it gets narrowed until it
is. "Most of the advice I run into is about the first one" is better than
"almost all the industry's energy", not because it's softer but because it's
defensible.

**Concede before the reader objects.** Name the counterargument yourself, in its
strongest form, then answer it. A post arguing that shared building blocks keep
a model from going wrong lists the four ways it can go wrong anyway, and that
concession is what makes the surrounding claim credible.

**Close by returning to the opening.** The last paragraph should make the first
one mean something it didn't mean at the time.

**Words to avoid:** "useful" more than twice in a piece, "leverage", "unlock",
"delve", "it's worth noting". Anything that sounds like it was written to fill
a paragraph.

## Structure that has worked

Scene → what it actually cost → what we built → the mechanism, stated as one
memorable line → the result with numbers → why it generalizes → what stays the
reader's job → honest limits → callback close.

When the argument is about specification, a before-and-after comparison is the
centerpiece. Both versions must describe the *same* thing; if the short one
omits something the long one carries, a reader will find it and conclude the
comparison was rigged. Audit them line by line before publishing.

## Evidence discipline

This is the series' whole credibility strategy. Hold it.

- Label what is **lived** and what is **conviction**, explicitly, in the text.
- State limits before a reader can raise them. A post reporting what two weeks
  of work produced says "two weeks says nothing about what that library costs to
  maintain" in Ryan's own voice, which is what makes the numbers above it
  believable.
- Ground claims about other teams or the industry in personal observation: "in
  the codebases I've worked in", not "teams tend to".
- Never state a product convention as a fact about the world. "We'd standardized
  on MM/DD/YYYY", not "there was exactly one correct date format".
- Never convert a reduction in risk into a guarantee. See the `review-draft`
  skill; this is the failure mode that recurs most.

## Style rules, non-negotiable

- **No em dashes.** Use a comma, colon, period, or parentheses. An en dash is
  not a substitute. Em dashes read as AI-written and undermine authorship.
- **Straight quotes only**, `"` and `'`, never curly.
- **American English.** Color, not colour. -ize, not -ise.
- Sentence case for headings.

## Files and conventions

The repo README is the source of truth; read it rather than guessing. In short:

- Standalone post: `posts/[date]-[name].md`
- Series post: `posts/series/[series-name]/[NN]-[name].md`
- `images/` and `social/` mirror `posts/`: one directory per post, named after
  the post's path with the leading `posts/` dropped.

  | Post | Images | Social |
  | --- | --- | --- |
  | `posts/2026-10-01-foo.md` | `images/2026-10-01-foo/` | `social/2026-10-01-foo/` |
  | `posts/series/bar/02-baz.md` | `images/series/bar/02-baz/` | `social/series/bar/02-baz/` |

  The hero is always `hero.png`. Reference it as `feature_image: hero.png`;
  paths resolve relative to the post's own image directory.

**Only if the post belongs to a series:** read
`_ideas/series/[series-name]/00-series-plan.md` first. It records the rules
earlier posts settled, which later posts must not contradict or re-derive, and
the evidence status of each planned post. A standalone post has no such file and
needs no equivalent.

## Referring to other posts in the series

**Never write "post 1", "post 3" or "post 4" in the post itself.** A reader
arrives from a search result or a link with no map of the series, so a number
identifies nothing. It also reads like filing-system prose rather than writing.

For a post that hasn't been published yet, name the topic: "a loop that deserves
a post of its own", "a later post turns on what happens when that list isn't
empty". The reader learns what is coming rather than that something is.

For a post already published, refer to it by phrase and vary the phrase. "The
first post in this series" on first mention, then "last time", "that post", or
the thing it was about, which is often the most informative option: "the design
system I wrote about last time" does more work than any number, and disambiguates
where several projects are in play. Where the idea can simply be restated, drop
the reference and restate it.

If a post refers back more than about three times, the references are doing work
the prose should do. Cut some rather than restyling all of them.

**Link twice, not every time.** Link the first mention and the last. A reader
who wants to navigate back does it before committing to the argument or after
seeing it pay off, not from the middle of a paragraph, and one URL repeated
eight times reads as filler.

## Frontmatter

```yaml
title: ...
slug: ...
meta_title: ...        # the theme appends " - Loud Trumpet", so ~45 chars max
meta_description: ...  # 140-160 characters
feature_image: hero.png
audience: ...          # who it is for and what they are assumed to know
tags: [...]
excerpt: ...
```

`audience` never reaches Ghost. The publisher builds its payload from an
explicit allowlist, and a pull carries unknown keys forward, so the field lives
with the post without appearing on the site.

Every technical term in a draft has to survive one of two tests against that
line: it carries the argument, or it is glossed in place. A term that does
neither is set dressing, and set dressing narrows the audience for nothing.
"Markdown" carries an argument about why plain text with structure works, so it
stays and earns six words of explanation. "A library you considered and
rejected" was one item in a list of three examples, so it became "a tool" and
cost the technical reader nothing.

`meta_title` and `meta_description` are the search result. Count the site suffix
against the title budget, and keep `meta_title` starting with the post's own
title: a search result that promises something different from the heading reads
as a bait and switch, and Google often rewrites a title tag it judges
unrepresentative of the page.

`meta_description` also fills the link preview text on LinkedIn and X, so one
field normally covers search and social both. Only set `og_description` or
`twitter_description` when a card should read differently from a search result:
around 100 to 120 characters, written to earn a click rather than summarize.
That is the exception, not the habit. `og:title` has no equivalent and follows
`meta_title`.

## Before handing a draft over

Run the `review-draft` skill against it. At minimum: no em dashes, no curly
quotes, no unqualified claims, and the before/after examples describe the same
thing.

Also check that nothing survives from the interview stage: no placeholder
markers, and no example, number or outcome that came from anywhere but an
answer Ryan gave.

There is no `status` field: publication state lives on each Ghost target, not in
the file. Publishing to local always makes a post visible there, publishing to
live always creates a draft, and `npm run ghost promote` is the separate command
that puts something in front of readers. Never run it unless asked in the
conversation.
