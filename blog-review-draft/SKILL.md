---
name: blog-review-draft
description: Audit a Loud Trumpet draft before publishing, for overclaiming, style violations, internal contradictions and rigged examples. Use before any post goes live, or when asked to review writing.
---

# Reviewing a draft

Report findings ranked by how much damage each does if published. Don't rewrite
unless asked; the author decides.

## 1. Unqualified claims, the failure mode that recurs most

Every draft so far has converted a reduction in risk into a guarantee. Hunt
these specifically:

- **Impossibility claims.** "That bug can't happen." "Nothing gets quietly
  dropped." A mechanism removes a *class* of error through *one interface*. It
  doesn't stop every path to the same outcome. Bound the claim, and name the
  paths that remain open. Conceding them buys back the sentence.
- **Claims about populations.** "Most designers aren't good at CSS." "Teams tend
  to skip this." Rewrite as a limit on the author's evidence or as personal
  observation.
- **Claims about how tools behave.** "Most tools carry memory across sessions."
  "The tooling will offer to compact it." "Ending a session clears it." These
  are population claims wearing a technical costume, and they are the ones that
  slip through, because they sound like description rather than assertion. The
  AI landscape is not uniform and changes monthly, so scope every one of them to
  the tools the author actually uses, or name the tool. A reader following a
  prescription that is false for their product is the worst outcome a post here
  can produce.
- **Universal negatives.** "No description is ever complete." Reframe as where
  the burden falls, not what is possible.
- **Product conventions stated as facts.** "There was exactly one correct date
  format" should be "we'd standardized on".
- **Capability confused with habit.** "A summary I cannot fully check" when the
  truth is one the author did not read. "Cannot" blames the tool for a choice
  the author made, which is both inaccurate and, in a post built on admitting
  things, a wasted admission. Check every "cannot", "there is no way to" and
  "it does not let you" against whether the author simply did not.
- **Agency laundered through the passive.** "The draft was revised." "Mistakes
  were made." "The post was written out of an interview." Ask who performed the
  action, then name them. In a post that discloses AI involvement, an
  unattributed action reads as something the model did and the author declined
  to say so, which is worse than whatever the truth was. Watch for the reverse
  too: a sentence crediting Ryan with work a model did is a false claim, not a
  voice fix.
- **Proven versus predicted.** Find every place the text implies evidence it
  doesn't have. The blog's credibility rests entirely on this line being drawn
  in the right place, in a standalone post as much as in a series.

## 2. Internal contradictions

Read the piece as a hostile reader with a good memory.

Real example: a draft argued that anything encoding company-specific commitments
shouldn't be a shared block, eleven paragraphs after praising a date picker
wrapper that encoded exactly that. Both sentences were fine alone.

**If the post belongs to a series**, also check it against
`_ideas/series/[series]/00-series-plan.md`, which records the rules earlier posts
settled. A later post may extend them; it must not silently contradict them, and
it should not re-derive what an earlier post already established. A standalone
post is only checked against itself.

## 3. Caveats bolted onto claims they contradict

The most common damage a revision pass does, and it is invisible unless you read
for it, because every individual sentence is defensible.

It looks like this. A draft says a thing confidently. Someone points out the
claim is too strong. The fix arrives as a new paragraph underneath: "I should
not oversell this", "one thing breaks the analogy", "that said". The original
sentence is untouched. The post now says two incompatible things, and a reader
who gets to the second one stops trusting the first.

Three of these appeared in a single draft: short sessions were safe and then
unsafe, ending a session cleared everything and then did not, a transcript did
not record a rejection and then did.

**The fix is to change the claim, not to append to it.** If short sessions are
usually safe, the sentence says usually. If ending a session clears one thing
and not another, the sentence says which. A caveat earns its place when it adds
something the claim cannot carry, such as a limit on the evidence. It does not
earn its place by contradicting the sentence above it.

Flag any paragraph opening with a concessive move and check what it is conceding
against. If the answer is "the previous paragraph", that previous paragraph is
the thing to rewrite.

The miniature version of this is an aside, usually the last clause of a
sentence, that concedes something the post cannot afford while sounding like
voice. "Rather than what I have since talked myself into" recast every rule the
author had written as a rationalization. Read each of these on its own, ask what
it gives away, and cut the ones that are paying in argument for a joke.

## 4. Rigged comparisons

When a draft contrasts a bad approach with a good one, both sides must describe
the same thing. Diff them item by item. Anything the good version omits must be
something a reader would agree is genuinely handled elsewhere, and where that
isn't obvious, the text should say so.

One post's before-and-after spec comparison was unfair in its own favor by
accident: the long version was underspecified, which made the short one look
better than it was. Filling both out made the contrast stronger, not weaker.

## 5. Style, mechanical

- Em dashes: zero. Check with a literal search, they are easy to miss.
- Curly quotes: zero. Same.
- American English.
- Filler words, especially "useful" repeated.
- Hedges: "maybe", "might", "probably", "sometimes".
- Bold: sparing. Check what's emphasized is worth the weight, and that no
  unsupported claim is bolded.

## 6. Terms the audience was not promised

Read the `audience` line in the frontmatter, then read the draft as that person.
Every technical term has to pass one of two tests: it carries the argument, or
it is glossed in place. Flag the ones that do neither.

Do not flag a term merely for being technical. A post written for engineers is
allowed to use their vocabulary without apology, and a post written for everyone
is still allowed a term it cannot do without, as long as the reader is told what
it means the first time. What gets flagged is a word that narrows the audience
while carrying none of the weight, which is nearly always an example rather than
a claim.

If the draft has no `audience` line, say so. It should have one.

## 7. Unpaid promises

Any "I'll come back to it" or "more on that below" must actually be paid off.
Either write the payoff or cut the promise.

## 8. Specifics that aren't

Flag vague nouns where a real one is available: "a library" when the name is
known, "faster" with no baseline, "we moved fast" quoting language the reader
never saw.

## 9. Flow, read end to end

Do this last, in one pass, without stopping to fix anything. The checks above
are local and a draft can pass all of them while reading as a pile of correct
paragraphs that do not follow one another.

What to watch for:

- **A paragraph that does not connect to the one before it.** Usually a symptom
  of an edit that moved a sentence away from the setup it depended on. One
  draft's confession about staying in dead sessions became inexplicable when the
  line about being willing to end them was separated from it by an aside.
- **A term or reference used before it is introduced**, which happens when
  material is cut from above it rather than below.
- **The same admission made three times** in three different sentences, which is
  what repeated correction passes produce. Keep the sharpest one.
- **An argument that arrives before its setup**, or a payoff whose setup was
  deleted.

**After changing any sentence, re-read the paragraph it sits in and the one
before it.** A correction that fixes the sentence and contradicts its neighbors
is the single most repeated error in this repo's history. One sentence about a
transcript took three passes precisely because each fix was checked on its own
and never against the example three sentences above it.

Read the changed sentence whole as well, not just the part that was edited. A
rewrite that repairs the problem and leaves two "so"s, or the same verb twice,
is a new defect delivered by the fix. Most of these are invisible while editing
a fragment and obvious the moment the sentence is read start to finish.

## Reporting

Group as: fix before publishing / fix when convenient / mechanical. For each,
quote the line, say what's wrong in one sentence, and say why it matters to this
reader. Suggest a replacement only where the fix isn't obvious, and keep the
author's voice rather than substituting your own.
