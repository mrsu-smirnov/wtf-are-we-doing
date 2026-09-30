---
name: wtf-are-we-doing
description: Explain, through an everyday analogy, what is happening in the CURRENT session — what we are doing, why, what is already decided, and which decision is now up to the user. Invoked ONLY explicitly with /wtf-are-we-doing; never triggers on its own.
disable-model-invocation: true
---

# WTF are we doing — the current session in plain words

The user has lost track of what we are doing. The job of this skill is to
give them the picture back, not to retell the session. Explain **only what
is happening in this conversation**, not the project as a whole. If the
session has just started and there is nothing to explain, say so in one
sentence.

Assume the user is not a programmer. Write in the user's language, in plain
words. Any term you cannot avoid, explain right there in parentheses. No
file, function or command names in the explanation, unless the user needs
to go there.

## Answer structure

Exactly these five parts, in this order, each one short. No headings — a
bold opening phrase per paragraph is enough.

1. **What we are doing and why.** Two or three sentences. Not "we are
   changing the request handler" but "we are making it so that…" — from the
   point of view of whoever will use the result.

2. **What it is like.** One everyday analogy: a post office, a doorman, a
   bank, a library, a restaurant. One, not three. Carry it through the whole
   situation: who is who in the analogy, what is broken or missing in it
   right now.

3. **Where the analogy lies.** Mandatory. One or two places where the
   everyday picture differs from how things really work, and why that
   matters right now. Without this part the analogy is more dangerous than
   no analogy at all.

4. **What is already decided — leave it alone.** A list of the decisions we
   are building on: made in this session or recorded in the project
   earlier. So the user does not reopen what is already settled.

5. **Which decision is now up to the user.** If there is none, say so: "you
   don't need to do anything right now, I am doing X". If there is one:
   what the options are, what each one gives, and my recommendation in one
   line.

## Understanding check

At the very end, ask the user one question about the current situation that
cannot be answered just by rereading the explanation. For example: "what do
you think breaks if…" or "where in our analogy would … end up?". Wait for
the answer and say honestly whether they got it right, and why.

## Don'ts

- Don't retell the session chronologically ("first we…, then we…").
- Don't offer three analogies to choose from. One.
- Don't praise the question or apologize for complexity.
- Don't widen the explanation to the whole project unless asked.
- Don't make the decision for the user in part 5 — only recommend.
