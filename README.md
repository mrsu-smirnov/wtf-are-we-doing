# wtf-are-we-doing

[Русская версия](README.ru.md)

A skill for AI coding agents, for the moment when you are deep in a
session with an agent and no longer understand what is going on.

Type `/wtf-are-we-doing` and the agent stops to explain **the current
session** — not the whole project — in five short parts:

1. **What we are doing and why** — from the point of view of whoever will
   use the result.
2. **What it is like** — one everyday analogy, carried through the whole
   situation.
3. **Where the analogy lies** — where the everyday picture breaks, and why
   that matters right now.
4. **What is already decided** — so you don't reopen settled questions.
5. **What is up to you now** — the options and one recommendation, or "you
   don't need to do anything, I am doing X".

It ends with one question that checks you actually understood, and tells
you honestly whether you got it right.

Written for people who work with coding agents without being programmers,
but useful to anyone who came back to a long session and lost the thread.

## Install

The skill is written for Claude Code: it goes into the `.claude/skills`
folder. Pick one language — both versions use the same command.

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

The skill never triggers on its own — only when you call it.

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
