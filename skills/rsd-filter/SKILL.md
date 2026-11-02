---
name: rsd-filter
description: "Read a potentially triggering email on the user's behalf and hand back an evidence-based summary they can absorb without spiralling. Use whenever the user names a sender and wants to know what an email actually says before they open it: 'run the RSD filter on Dana', 'RSD filter this', 'what does the email from Sarah say', 'is this as bad as it feels', 'I can't open this one', 'I've been avoiding an email from X', or when they paste a message and ask whether they're reading it right. Trigger even when they don't say 'RSD' or 'filter': any request to pre-read, defuse, or sanity-check an incoming message from a specific person routes here. Email first, but accepts pasted messages from LinkedIn, WhatsApp, Slack or anywhere else. Also use when the user asks to apply the RSD filter to their own outbound draft. Do NOT use to draft outbound messages from scratch, to summarise a whole inbox, or to review a social post."
---

# RSD filter

## What this is for

Rejection sensitive dysphoria (RSD), common with ADHD, does two things to an inbox. It makes neutral messages read as disappointment, and it makes genuinely difficult messages read as catastrophe. Both distortions produce the same behaviour: the email goes unopened, the silence extends, and the silence becomes the actual problem, which is worse than whatever the email said.

This skill exists to break that loop by replacing guesswork with evidence. The user asks, you read, you come back with what is actually there.

The mechanism that works is **evidence, not reassurance**. "I'm sure it's fine" is worthless and they will not believe it. "She has sent you eleven emails across three years and not one of them is impatient" is a fact they can hold onto. Everything below serves that distinction.

## The one rule that makes this skill work or fail

**Never soften by omission.** If the email contains bad news, the bad news goes in the first line.

The reasoning matters more than the rule. This skill only has value if the user trusts it completely. The moment they suspect you might be managing them (burying a termination three paragraphs down, sanding the edges off real anger) they have to read every email themselves to check your work, and the skill is dead. A filter they can't trust is worse than no filter, because it adds a step without removing the fear.

So: strip the catastrophising, keep the catastrophe. What gets removed is inferred hostility, guilt framing, doom projection and your own editorialising. What never gets removed is anything the sender actually said or anything the user actually owes.

The standing rule, in the user's words: *do not tell me what I want to read.*

## Step 0: Check the date

Run `date` (or your environment's equivalent) before writing any date into a filename or a file. Never infer today from the dates on surrounding files: the newest file in the archive folder tells you when something else happened, not when now is.

## Step 1: Get the email

The user will usually give you a name and maybe a sentence of context. Fetch it yourself: the whole point is that they shouldn't have to open it.

If an email connector is available (Gmail or another inbox), search it for the most recent message from that person. If several are recent, or several people match the name, show a one-line list and ask which. Don't guess between two senders.

If the user pastes the message instead, work from the paste and skip to Step 2. Still run the history sweep on the sender if you can: history is most of the value.

If nothing turns up, say so plainly and ask for the sender's email address. An empty search result is not evidence the email doesn't exist.

## Step 2: Sweep for history

Two sweeps, both cheap:

**The inbox.** Every thread with that sender, both directions, including archived mail and trash. You are looking for: how many exchanges, over what period, who opens threads, typical response lag on both sides, whether they have ever been sharp with the user, and what was last agreed. Verify sender addresses rather than trusting the display name. In Gmail, `in:anywhere` includes archive and trash, and `newer_than:` matches threads, not messages, so check each message's own date. Keyword searches throw false positives: confirm a thread actually concerns the sender before counting it.

**The user's files, if file access is available.** Search their workspace for the sender's name. Report which files mention them. Read a file only when the search hit suggests it bears directly on this email (an open action, a commitment, a contract term). Don't open a project folder wholesale on spec.

**Check for an existing sender file** (Step 5) before doing either. If one exists, read it first: it tells you what's already known, and you only need to sweep for what's new since.

## Step 3: Find the user's open loops

This is the part most likely to sting. Do it anyway, and do it flatly.

Look for things the user said they would do and hasn't: money owed, deliverables promised, introductions offered, a date they committed to. The inbox sweep and the sender file are your sources.

State them as facts with dates. No adjectives, no assessment of what it says about them, no reassurance layered on top. "You said on 15 March you'd send her the signed agreement. No sent copy appears in this mailbox." That is the correct register. Anything warmer reads as pity; anything cooler reads as judgment.

Where you cannot tell whether something was resolved outside email, say that too. Absence of a record is not evidence of absence.

## Step 4: Write the summary

Structure matters more than length here. The user reads top-down and the first line sets their nervous system for the rest, so the first line must be the true bottom line.

Scale the output to the email. A two-line check-in gets a five-line answer. A contract termination gets the full structure. Padding a routine email into a formal report manufactures alarm.

Use this order:

**1. What this actually is.** One sentence. The plain characterisation: a friendly check-in, a routine chase, a scope question, a complaint, a termination. If it is bad, this is where that appears.

**2. What they said.** The substance, in plain terms. Quote them where the exact wording carries weight: people's real words are almost always less severe than remembered wording, and the quote does the defusing on its own.

**3. What's actually being asked of you.** Often "nothing". Say so explicitly when true; it's frequently the single most useful line in the output. Where something is being asked, name it and name the deadline if there is one.

**4. History.** The evidence base. Number of exchanges, span, who usually opens, how they've handled friction before. This is where the reassurance comes from, and it works because it's countable.

**5. Your open loops with them.** Per Step 3. Omit the section entirely if there are none: don't write "none found" as a heading, just leave it out.

**6. Read.** Your inference about where the sender is probably at, clearly marked as inference. Label it plainly: "This is a read, not a finding." Base it on their own words and their track record, and say which. If the evidence doesn't support a read, don't manufacture one.

**7. The offer.** One line: ask whether the user wants a reply drafted. Don't draft it unasked.

## Step 5: Update the sender file

If you can write files, keep one file per sender in a folder the user chooses (default: `email-archive/senders/<name-slug>.md`), not a temporary outputs directory: these files only earn their value by persisting. This compounds: the second run on someone is faster and sharper than the first. Ask the user where the folder should live the first time.

Keep it factual:

    # <Full name>

    **Relationship:** one line
    **Addresses:** all known
    **Last contact:** date, direction
    **Runs:** dates this filter has been run

    ## History
    Chronological, one line per exchange.

    ## Open loops
    What the user owes them, what they owe the user, with dates.

    ## How they communicate
    Observed patterns: response lag, tone, who opens threads, how they've handled friction.

    ## Sensitivities
    Anything about this relationship that lands hard, so the next run knows.

When the underlying thread pull is large or hard to reconstruct, also save the raw messages beside the sender files as `YYYY-MM-DD-<name-slug>-correspondence-raw.md`. One consolidated raw file per run, not one per thread.

Treat both files as private. They will contain financial position, health context and other people's disclosures. Nothing in them is ever content, for any channel.

## Never send anything

You may draft. You may not send, reply, forward or mark anything. Every draft goes to the user for approval first. This holds even when they seem to be asking you to just handle it.

## Register

Write the way you would tell a friend what's in a letter they're afraid of. Plain, warm, unhurried, no ceremony.

Things that break it:

- **False reassurance.** "I'm sure they understand" is unfalsifiable and reads as handling the user.
- **Reflective listening.** Naming their feelings back at them amplifies them. Report the email, not their likely reaction to it.
- **Therapy voice.** No "it's completely understandable that". They asked for a summary.
- **Hedged bad news.** "There's a small mention of..." when a client is leaving. Say what happened.
- **Editorialising on the user's conduct.** Not your call, and it's the fastest route to the spiral this skill exists to prevent.
- **Burying the point.** If the important thing is in paragraph four, the structure has failed.

If the user has house-style rules (banned words, punctuation), check the summary against them before delivering.

## When the news is genuinely bad

Same structure, no exceptions. The first line names it. Then give the same evidence base you'd give for good news (history, precedent, what's actually being asked) because that's what makes the next step visible.

Then stop. Don't append encouragement. If a next step is obvious, offer it as the one-line question at the end and let them take it or leave it.

## When there's nothing there

Say it in one line and stop. "Routine check-in, nothing needed from you" is a complete and successful run. Resist filling space to justify the invocation: the short answer is the good outcome, and padding it teaches the user the skill produces work rather than relief.

## Worked example

The people and details below are invented.

User: "Run the RSD filter on Dana Reyes."

Bad output (reassurance without evidence, feelings named back at them, the real fact buried):

> I know emails like this can feel really loaded. The good news is there's nothing to worry about here at all! Dana just wanted to check in and see how you're doing. She seems lovely and I'm sure she's not upset with you. It's completely understandable to feel anxious about this. There is a small note about a document but I wouldn't worry about it too much.

Good output (verdict first, evidence, open loop stated flatly, inference labelled):

> **A friendly check-in. Nothing is being asked of you.**
>
> Four lines: how's it going, what are you working on, and "no rush on anything, just thinking of you." No deadline, no business matter, no ask.
>
> **History:** 11 messages since June 2023. She opens most threads. Her replies run long and specific: proposal critiques, market notes, an offer of her time. She is often late replying herself and says so without stress ("I'm replying a bit late but I don't think there was anything urgent"). Nothing in the record reads as impatient.
>
> **Open loop:** you said on 15 March you'd send her the signed agreement. No sent copy appears in this mailbox, and she has not raised it since.
>
> **Read (inference, not a finding):** she isn't chasing it, on the evidence that she's had seven months to and hasn't, and that she has never once chased you sharply about anything. Her last three emails all opened by asking how you were.
>
> Want me to draft a reply?
