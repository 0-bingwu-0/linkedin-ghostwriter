# LinkedIn Ghostwriter

Good LinkedIn posts usually come from your own work: something you built, a mistake you learned from, a call you made. You have plenty of these. Turning one into a post every week is the hard part. Then you want it on X too, and X needs a different version.

This project has AI do that with you. It helps you pick a topic, writes the LinkedIn post in your voice, and once you approve it, turns it into an X Post or X Article.

## Getting started

Open this project in StashBase and tell the Agent:

1. **"Set me up."** It asks you a few questions, one at a time: who you are, what you want to post about, who you want to reach, how you sound, what to avoid, and whether you have X Premium. Then it makes the project yours. Paste a few of your past LinkedIn posts when it asks how you sound, and it'll match your style better.
2. **"What should I post?"** It asks what you've been working on or learning lately. Tell it in a sentence or two, and it suggests a few ways to write it. Nothing comes to mind? Say **"Find what's hot."** It pulls the last 24 hours of posts from the X accounts you follow and suggests topics that connect to your work. On the first run, it asks whether you want to set up the [X API](#x-api). If you'd rather skip it, paste a post you came across.
3. **"Write it."** Or tell it what you want to write about. It writes a LinkedIn post and saves it to `output/linkedin_posts.md`. If one detail only you know would make the post much better, it asks you first. Ask for any edits you want, like "Make the opening more casual."
4. **"Approved."** It turns the post into an X Post or X Article, whichever fits, and saves it to `output/x_posts.md` or `output/x_articles/`.

The template comes with an example setup: a computer science student who learns AI by building with it and wants to share what they learn. You can try it as is before running setup.

## Make it yours

Setup covers most of it. You can also change things anytime:

* **Your background and writing style** are in `context/profile.md`. Edit it, or just tell the Agent. When you correct how something is written, it remembers.
* **Past posts** go at the top of `output/linkedin_posts.md`. 10–20 that best show your style is enough. Past X posts go in `output/x_posts.md`, and X Articles in `output/x_articles/`.
* **The accounts you follow** for finding what's hot are in `workflows/topics.md`. Change them to sources in your field, or send the Agent your list.
* **The Agent's persona and rules** are in `AGENTS.md`.

## X API

Finding what's hot needs [Node.js](https://nodejs.org) 20.12+, an Agent that can run local commands, and an [X API](https://developer.x.com) Bearer Token with prepaid credits.

[X API pricing](https://docs.x.com/x-api/getting-started/pricing) is $0.005 per post read: fetching 20–100 posts costs about $0.10–$0.50 in post reads. The script fetches up to 500 posts per run ($2.50 in post reads) and prints that estimate. Returned user records are billed separately at $0.01 each; Agent usage is separate.

Put the token in a `.env` file in the project root (it's in `.gitignore`, so it won't be committed):

```bash
X_BEARER_TOKEN=your-token-here
```

## Files

* `AGENTS.md`: the AI's persona, how it writes for you, and the task index.
* `CLAUDE.md`: points Claude Code to `AGENTS.md`.
* `context/profile.md`: your background, posting goals, posting angle, writing style, and X Premium setting.
* `workflows/setup.md`: the setup Q&A.
* `workflows/topics.md`: how to find topics from your work or what's hot, including the X accounts you follow.
* `workflows/write.md`: how to write LinkedIn posts.
* `workflows/repurpose.md`: how to turn an approved LinkedIn post into an X Post, Thread, or X Article.
* `workflows/scripts/x-search.mjs`: pulls recent posts from the given accounts.
* `output/linkedin_posts.md`: your past LinkedIn posts and new ones.
* `output/x_posts.md`: X Posts and Threads.
* `output/x_articles/`: X Articles, one file each.
