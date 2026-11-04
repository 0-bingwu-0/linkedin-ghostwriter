# LinkedIn Ghostwriter

Good LinkedIn posts usually come from your own work: something you built, a mistake you learned from, a call you made. Often it starts with a feeling about your work, and the examples that back it up are buried in the work itself.

This project has AI help with all of it. Tell it an idea when one strikes you. When you want to post it, it finds examples in your work notes, asks you for what's missing, and writes the LinkedIn post in your voice. Whatever you tell it about yourself and your work, at any point, is kept, so you only explain something once. Each time it saves something, it tells you what and where, so you can correct it.

## Getting started

Open this project in StashBase and tell the Agent:

1. **"Set me up."** It asks you three quick questions, one at a time: who you are and what you work on, what you want to post about, and a few of your past LinkedIn posts so it can match your style. Then it sets up your profile and saves your past posts, and asks for your first idea.
2. **"I have an idea: …"** Whenever something about your work strikes you, a sentence is enough, like "I have an idea: working code is only the starting bar in someone else's repo." It saves it to your ideas on the dashboard, and if it isn't clear how you'd tell it, asks how you plan to write it.
3. **"Write about …"** Name the idea, like "Write about small PRs." It looks for examples in your work notes and asks you for what's missing, like which PR or what broke. What you add is saved to `context/work/`, so you won't have to explain it again. Then it writes the LinkedIn post and saves it to `posts/`, one file per post. Ask for any edits you want, like "Make the opening more casual."

Open the dashboard, `index.html`, to see what's next: ideas waiting to be written, drafts waiting to go out, and what you've posted.

The template comes with an example: a software developer a month into contributing to open source, with notes on that work, a few ideas including a series, a draft, and some past posts. Setup replaces it with yours.

## The dashboard

Everything works in Chat, and you never have to open anything else. The dashboard shows where each post is at, kept current by the Agent.

* **Ideas:** your ideas waiting to be written. Just tell the Agent one. Click one to see it from the side, with how you plan to tell it, or to drop it. A series, like an intro, three examples, and a wrap-up, stays here with its plan until the last post is written.
* **Drafts:** posts written but not out yet. Click one to open it.
* **Posted:** what's out, newest first, past posts included. Tick a draft's circle once you've posted it, or just tell the Agent.

Switch to **All posts** to see every post in one table, with its status and the day it went out.

## Make it yours

You can change things anytime:

* **Your background and writing style** are in `context/profile.md`. Edit it, or just tell the Agent. When you correct how something is written, it remembers.
* **Your work notes** are in `context/work/`, organized by project, like `open-source.md`. You can edit them yourself too.
* **Your posts** are in `posts/`, one file per post, named like `2026-11-04-first-month-sending-prs.md`. Past posts can go there too, or just paste them to the Agent. 10–20 that best show your style is enough.
* **The Agent's persona and rules,** including how it keeps your profile and work notes, are in `AGENTS.md`. How it keeps the dashboard is in `workflows/maintain.md`.

## Files

* `context/work/`: what the Agent knows about your work, organized by project.
* `context/profile.md`: your background, posting goals, posting angle, and writing style.
* `posts/`: your LinkedIn posts, past and new, one file each.
* `workflows/setup.md`: the setup Q&A.
* `workflows/idea.md`: what happens when you tell it an idea.
* `workflows/write.md`: how to write and edit LinkedIn posts.
* `AGENTS.md`: the AI's persona, how it writes for you, the task index, and how it keeps your files.
* `CLAUDE.md`: points Claude Code to `AGENTS.md`.
* `workflows/maintain.md`: how the Agent keeps the dashboard current, and the format of its data.
* `index.html`: the dashboard.
* `assets/`: the dashboard's data and banner.
