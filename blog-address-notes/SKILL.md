---
name: blog-address-notes
description: Find and act on Ryan's inline notes in a draft, left in square brackets in the file. Use when he says he has left comments, notes, questions or feedback in a post, or asks for those to be reviewed or addressed.
---

# Addressing notes in a draft

Ryan reviews in the file rather than in chat. He leaves notes in square brackets,
inline, at the exact point they apply to. This skill is how those get found,
acted on, and reported back.

## Finding them

```bash
grep -n '\[' <file>
```

Then discard the false positives by eye. Two kinds exist:

- **Markdown links**, `[the design system post](/compose-dont-create/)`. Bracketed text
  immediately followed by `(` is a link, not a note.
- **Code inside fences**, array syntax and the like.

A note is bracketed prose, usually a fragment, dropped mid-sentence:

```text
... it reached for our `FlexBox` [this isn't exactly true - one used RN
primitives], and assembled them ...
```

Notes appear in frontmatter, in headings, and inside code blocks, so search the
whole file rather than the body. **Read the full file, not only the matching
lines.** A note often refers to something several paragraphs away, and the fix
usually lands somewhere other than where the note sits.

If the search finds nothing, say so rather than guessing at what he meant.

## Sort before acting

Split the notes into two piles, because they cost different amounts:

**Notes that change a fact.** "This isn't exactly true." "That was never in
scope." "It was three pages, not two." These are the expensive ones. One of them
can invalidate sentences elsewhere in the post, the series plan, or an already
published post. After applying one, search the file for the old fact and for
anything that depended on it.

**Notes that change wording.** Clarity, phrasing, a word that lands badly. These
are local and can be applied directly.

Do the fact notes first. A wording fix to a sentence that a fact note is about to
delete is wasted.

## Every note gets one of three outcomes

1. **Applied.** Make the change and delete the bracketed text. A note left in the
   file ships.
2. **Not applied, with a reason.** Ryan wants disagreement when it's warranted,
   stated in a sentence and then dropped. Don't apply something you think is
   wrong just because he asked; say why and let him decide.
3. **Asked.** If a note is ambiguous, ask rather than picking a reading. Applying
   the wrong reading costs more than one question.

Never silently skip a note, and never report a note as applied when what actually
happened was an approximation of it.

**A note phrased as a question is a question.** "Can this be removed now, right?"
and "or am I just reading this weird?" want an answer and a recommendation, not
silent compliance. Answer it, then say what you did.

## When a note supplies a fact

Use exactly what he gave, and nothing more. If the note says three pages, the
post says three pages: not "several", not "a handful", and not a second invented
number somewhere else to match. The evidence discipline in `blog-write-post`
applies to every sentence a note touches.

If a note reveals that something in the post was invented rather than reported,
check the rest of the post for the same failure before reporting back.

## Applying a correction

**Change the sentence the note is about. Do not add a sentence next to it.**
When a note says a claim is too strong, the tempting fix is a caveat underneath:
"that said", "I should not oversell this". The original claim survives, the two
sentences contradict each other, and the draft is worse than before the note was
written, because now it is visibly arguing with itself. Rewrite the claim so it
is true as stated.

**Then re-read the paragraph the change sits in, and the one before it.** A fix
checked only against the note frequently contradicts its own neighbors. One
sentence in a recent post needed three passes for exactly this reason: each
rewrite was correct on its own and fought with an example three sentences above
it that nobody re-read.

## After applying

- Re-run the search. No brackets should survive except real markdown links.
- Mechanical pass: em dashes, curly quotes, hedges, American English.
- **The series plan.** If a note changed a settled fact, update
  `_ideas/series/[series]/00-series-plan.md` so later posts inherit the corrected
  version rather than the original.
- **Published posts.** If a note contradicts something already live, say so and
  ask before republishing.

## Reporting back

Order by how much each note changed, not by where it sits in the file.

1. Notes that changed a fact, with what else had to move because of them.
2. Notes where the change wasn't exactly what was asked for, and why.
3. Anything not applied, with the reason.
4. Questions.
5. Wording changes, briefly and in a group. These don't need a line each.

Quote enough of each note to be identifiable. Don't paste the whole diff; he has
the file open.
