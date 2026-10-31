# RSD filter: a Claude skill

Some emails don't get opened. Not because they're bad, but because they might be.

Rejection sensitive dysphoria, common with ADHD, makes a neutral email read as disappointment and a difficult one read as catastrophe. Either way the email sits unopened, and the silence becomes the real problem. This skill opens it for you and tells you what's actually there.

## How it works

- **Evidence, not reassurance.** "I'm sure it's fine" is worthless. "She has sent you eleven emails in three years and not one is impatient" is something you can hold onto.
- **Bad news goes in the first line.** It strips the catastrophising and keeps the catastrophe. A filter you can't trust is worse than no filter.
- **It checks the history:** how many exchanges, who usually opens, how they've handled friction before, and what you've said you'd do and haven't, stated flatly with dates.
- **The summary runs in a fixed order:** what this is, what they said, what's being asked of you (often nothing), the history, your open loops, a clearly labelled read on where they're at, and an offer to draft a reply.
- **It never sends anything.** Drafts only, and only when you ask.
- **It remembers.** One file per sender, so the second run on someone is faster and sharper than the first.

## Using it

Copy `skills/rsd-filter` into your Claude skills folder (`~/.claude/skills/` or your project's `.claude/skills/`). It works best with an email connector such as Gmail, and also takes pasted messages from anywhere. Then: "run the RSD filter on [name]".

## Licence

MIT. See `LICENSE`.
