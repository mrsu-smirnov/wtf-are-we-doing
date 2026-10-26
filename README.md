# wtf-are-we-doing

[Русская версия](README.ru.md)

A skill for AI coding agents, for the moment when you are deep in a
session with an agent and no longer understand what is going on.

Type `/wtf-are-we-doing` and the agent stops to explain **the current
session**, not the whole project, in five short parts:

1. **What we are doing and why**, from the point of view of whoever will
   use the result.
2. **What it is like:** one everyday analogy, carried through the whole
   situation.
3. **Where the analogy lies:** where the everyday picture breaks, and why
   that matters right now.
4. **What is already decided**, so you don't reopen settled questions.
5. **What is up to you now:** the options and one recommendation, or "you
   don't need to do anything, I am doing X".

It ends with one question that checks you actually understood, and tells
you honestly whether you got it right.

Written for people who work with coding agents without being programmers,
but useful to anyone who came back to a long session and lost the thread.

## Example

Someone is building a small online shop for handmade candles. For half an
hour the agent has been changing something in checkout, and words like
"stock", "transaction" and "race condition" keep flashing by. They type
`/wtf-are-we-doing`:

> **What we are doing and why.** We are making sure the last candle can't
> be sold twice. Right now, if two customers check out at almost the same
> moment, both pay, but there is only one candle.
>
> **What it is like.** A market stall and a notebook where the seller
> writes down what is left. A customer asks for a candle, the seller
> checks the notebook, sells it, crosses it out. The trouble is we have two
> sellers sharing one notebook: both looked, both saw "1 left", both sold.
>
> **Where the analogy lies.** Real sellers would notice each other. On the
> site, two orders arrive a fraction of a second apart and nobody sees
> anybody. So we need a rule "while one is writing in the notebook, the
> other waits", not attentiveness. And the notebook here is really the
> database (the place where the site keeps stock counts); it can enforce
> that rule by itself if asked.
>
> **What is already decided, leave it alone.** Payment stays with the
> current payment service. Stock is counted in one place, not two.
>
> **What is up to you now.** What the second customer should see:
> (a) "Sold out" before paying: honest, but they may be disappointed;
> (b) accept both orders and make another candle within a week: more
> sales, but you have to keep up. I recommend (a): no refunds needed.
>
> Check question: a customer put the last candle in their cart and left for
> an hour to have tea. Do you think the candle is theirs during that hour,
> or still for sale?

## Install

The skill is written for Claude Code: it goes into the `.claude/skills`
folder. Pick one language; both versions use the same command.

macOS / Linux:

```bash
git clone https://github.com/mrsu-smirnov/wtf-are-we-doing
cp -R wtf-are-we-doing/en/wtf-are-we-doing ~/.claude/skills/
```

Windows (PowerShell):

```powershell
git clone https://github.com/mrsu-smirnov/wtf-are-we-doing
Copy-Item -Recurse wtf-are-we-doing\en\wtf-are-we-doing "$HOME\.claude\skills\"
```

For the Russian version, use `ru/` instead of `en/`. Restart Claude Code,
then type `/wtf-are-we-doing`.

Other agents that read skills in the `SKILL.md` format (Codex, bb and
others) use the same folder: copy `en/wtf-are-we-doing` into your agent's
skills folder. In bb, that is the `skills` folder inside the bb data
folder.

The skill never triggers on its own, only when you call it.

## How it differs from similar skills

- [catch-me-up](https://github.com/ktdrv/catch-me-up) narrates what the
  agent did while you weren't watching, step by step, and flags drift. This
  skill doesn't retell history: it tells you where you are and what is on
  you now.
- [teach](https://github.com/alexknowshtml/claude-skills/blob/main/teach/SKILL.md)
  runs a long Socratic quiz until you master the session. This skill is one
  short answer and one check question.
- [ELI5](https://github.com/dreambigou/eli5) and
  [explain-simply](https://github.com/yash2002vardhan/explain-simply)
  explain any topic simply. This skill explains only the session you are in.

## License

MIT
