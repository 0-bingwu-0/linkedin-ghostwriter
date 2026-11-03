# LinkedIn Ghostwriter

Good LinkedIn posts usually come from your own work: something you built, a mistake you learned from, a call you made. You have plenty of these, but by the time you sit down to write, you've forgotten most of them. And once a post is done, X needs a different version.

This project has AI help with all of it. Tell it what you did each day, and it keeps that in an inbox, suggests topics from it, writes the LinkedIn post in your voice, and once you approve it, turns it into an X Post or X Article.

## Getting started

Open this project in StashBase and tell the Agent:

1. **"Set me up."** It asks you a few questions, one at a time: who you are, what you want to post about, who you want to reach, how you sound, what to avoid, and whether you have X Premium. Then it makes the project yours. Paste a few of your past LinkedIn posts when it asks how you sound, and it'll match your style better.
2. **Tell it what you did today.** Make it a daily habit: a few sentences or a messy brain dump about what you built, learned, or ran into. It saves it to your inbox, one file per day in `inbox/`, and proposes one idea, from today or from earlier days you haven't posted about yet.
3. **"What should I post?"** Whenever you feel like writing, it pitches two or three ideas from your inbox, and you talk them through. If there's nothing new in your inbox, it asks what you've been up to. Nothing comes to mind? Paste a post you came across, and it suggests your own take on it.
4. **"Write it."** Once one clicks, it writes the LinkedIn post and saves it to `output/linkedin_posts.md`. If one detail only you know would make the post much better, it asks you first. Ask for any edits you want, like "Make the opening more casual."
5. **"Approved."** It turns the post into an X Post or X Article, whichever fits, and saves it to `output/x_posts.md` or `output/x_articles/`.
6. **"Update my stats."** Every week or two, export your LinkedIn analytics and drop the file into `stats/` first. It matches each post to its numbers and tells you what's working. Ideas lean toward what works, too.

Open the dashboard, `index.html`, to watch your inbox fill up and see what it's turned into. It shows these steps too.

The template comes with an example setup: a computer science student who learns AI by building with it and wants to share what they learn, with two months of their inbox, the posts it turned into, and how they did. You can try it as is before running setup.

## The dashboard

Everything works in Chat, and you never have to open anything else. The dashboard shows what you've been putting into your inbox and what's come out of it, kept current by the Agent. Every day and title opens its file.

* **Inbox:** a square for every day you wrote something down, colored by how far it went: written down, sparked an idea, or went into a post. Below it, one line for each day, newest first, with the ideas and posts it led to. Click a day to open its file.
* **Idea bank:** ideas waiting to be written. The Agent adds one each time you log a day. Have one of your own? Tell the Agent "Save an idea: …", and it tags it and links it to the days it builds on. Ask "What should I post?" to talk them through.
* **Posts:** everything you've written, with where it's at, its X version, and its impressions once you've updated your stats.

The impressions come from LinkedIn's own analytics export. On LinkedIn, open your profile's analytics, pick Past 365 days, and click Export. Drop the file into `stats/` and say "Update my stats."

## Make it yours

Setup covers most of it. You can also change things anytime:

* **Your background and writing style** are in `context/profile.md`. Edit it, or just tell the Agent. When you correct how something is written, it remembers.
* **Your inbox** is `inbox/`, one file per day, named like `2026-11-02.md`. You can write a day yourself too; the Agent adds it to the dashboard the next time it updates it.
* **Past posts** go at the top of `output/linkedin_posts.md`. 10–20 that best show your style is enough. Past X posts go in `output/x_posts.md`, and X Articles in `output/x_articles/`.
* **The angles your ideas and posts are tagged with** come from your posting angle in `context/profile.md`.
* **What the dashboard shows,** and how the Agent keeps it current, is in `workflows/maintain.md`.
* **The Agent's persona and rules** are in `AGENTS.md`.

## Files

* `AGENTS.md`: the AI's persona, how it writes for you, and the task index.
* `CLAUDE.md`: points Claude Code to `AGENTS.md`.
* `context/profile.md`: your background, posting goals, posting angle, writing style, and X Premium setting.
* `inbox/`: what you've been up to, one file per day.
* `workflows/setup.md`: the setup Q&A.
* `workflows/daily.md`: how your day gets saved to the inbox and turned into a topic.
* `workflows/topics.md`: how to find topics from your inbox, your work, or a post you share.
* `workflows/write.md`: how to write LinkedIn posts.
* `workflows/repurpose.md`: how to turn an approved LinkedIn post into an X Post, Thread, or X Article.
* `workflows/maintain.md`: how the Agent keeps the dashboard current, and the format of its data.
* `output/linkedin_posts.md`: your past LinkedIn posts and new ones.
* `output/x_posts.md`: X Posts and Threads.
* `output/x_articles/`: X Articles, one file each.
* `index.html`: the dashboard.
* `assets/`: the dashboard's data and banner.
* `stats/`: your LinkedIn analytics exports.
