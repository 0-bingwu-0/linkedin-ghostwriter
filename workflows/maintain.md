# Keep the Dashboard Current

The dashboard is `index.html`: my inbox day by day, the ideas it sparked, and the posts it turned into. A square for each day I wrote something down shows how far that day went. Every day and title opens its file. The page can't read the inbox, the posts, or the LinkedIn export, so what it shows comes from `assets/posts.json`, and keeping that file current is your job. What happened each day stays in its own file in `inbox/`, and the posts stay in `output/`. The JSON never repeats them: it holds a one-line summary of each day, the ideas, each post's date and topic for its link, and the posts' numbers. Which days went into which ideas and posts is kept only here, in their `from` lists. StashBase shows the change within a couple of seconds, even while the dashboard is open.

## When to update it

* **After saving my day to the inbox:** add the day's summary, or rewrite it if the day is already there, then add the idea you proposed. Both are steps in [daily.md](daily.md).
* **When you propose topics:** add each new one as an idea, as in [topics.md](topics.md#pick-topics).
* **When I give you an idea to keep,** like "Save an idea: why I stopped using flashcards": add it to the top of `ideas` with today's date, a `title` close to my wording, the `angle` it fits best, and in `from` any inbox days it builds on. Reply in a sentence, saying which angle and days you linked it to.
* **After writing a LinkedIn post:** add it as a draft with the days it used in `from`, and remove the idea it came from. This is the last step of [write.md](write.md).
* **After writing the X version:** set the post to approved and add its X version. This is the last step of [repurpose.md](repurpose.md).
* **When I tell you I posted something,** like "Posted the RAG one": set its `posted` date, today unless I say otherwise, and reply in a sentence.
* **When I drop an idea,** like "Skip the agents one": remove it.
* **When I say "Update my stats.":** follow [Update the stats](#update-the-stats).
* **When a post's topic or date changes:** change it in both the heading and the JSON, so the link still lands on it.
* **When a day's file changes,** or `inbox/` has a day the JSON doesn't, like one I wrote myself: rewrite that day's summary the next time you touch the dashboard. If a day's file is gone, remove the day, and take it out of every `from`.
* **When my posting angle changes:** update `focus` and `angles`.
* **At setup:** replace the example, as in [setup.md](setup.md).

## Update the stats

I export my analytics from LinkedIn and drop the file into `stats/`. Use the newest file there. Only read the files in `stats/`; don't edit, move, or delete them.

1. Read every sheet and check the real headers before taking any numbers. LinkedIn changes them from time to time. Usually there's a sheet of top posts, ranked once by engagements and once by impressions, each row with the post's link and publish date.
2. Merge the two rankings into one row per post.
3. Match each row to a post in the JSON. Use `url` if the post has one. Otherwise, match the publish date to `posted`, or to `date` if `posted` is empty. If two posts went out the same day, ask me which is which. Skip rows that match no post.
4. For each match, set `impressions` and `engagements` from the export, save its link as `url`, and set `posted` to the publish date if it's empty.
5. Reply in two or three sentences: the export's date range, which post did best and what might explain it, and anything that stands out, like one angle doing much better than the others. Use only numbers from the export.

If the export doesn't cover a post, leave its numbers as they are. If `stats/` is empty, tell me how to get the file, as in the [README](../README.md#the-dashboard).

## Editing rules

* Keep it valid JSON. Change only what you need, and leave every other field as it is, including fields not listed here.
* Dates are `YYYY-MM-DD`.
* Don't change `schemaVersion` or `index.html`.

## Format

```json
{
  "example": true,
  "focus": "What I learn about AI as a student who builds with it",
  "angles": [{ "id": "built", "name": "What I built" }],
  "inbox": [
    { "date": "2026-11-02", "summary": "Got my OS midterm back (84), and my roommate's databases slides broke the study helper." }
  ],
  "ideas": [
    { "date": "2026-11-02", "title": "My midterm came back, and the quiz mode was right", "from": ["2026-11-02"], "angle": "built" }
  ],
  "posts": [
    { "date": "2026-09-28", "topic": "What broke in my first RAG project", "from": ["2026-09-13", "2026-09-25", "2026-09-27"], "angle": "built", "status": "approved", "posted": "2026-09-29", "url": null, "impressions": 6420, "engagements": 263, "x": { "format": "article", "file": "2026-09-28-what-broke-in-my-first-rag-project.md" } }
  ]
}
```

* `example` is `true` only while the template's example is in place; the dashboard then also tells people to say "Set me up." Setup removes it.
* `focus` is my posting angle from [profile.md](../context/profile.md), in one short line.
* `angles` are the kinds of posts listed under "Posting angle" in profile.md, one for each kind. Each has an `id` and a `name` of a few words. Ideas and posts are tagged with one.
* `inbox` holds one entry per file in `inbox/`, newest first. Keep every day; the dashboard shows the recent ones and counts them all.
  * `date` is the file's name without `.md`. The dashboard links to `inbox/<date>.md`.
  * `summary` is the whole day in one sentence, under about 100 characters, in my words. It's a summary, not a copy: the details stay in the file.
* `ideas` are my idea bank: topics I haven't written yet, newest first. `date` is the day it was added, `title` is the topic in a few words, `from` lists the inbox days it builds on, and `angle` is the `id` of the angle it fits best. When I write one, remove it: the post takes its place.
  * You add every idea, whether you proposed it or I asked you to save it, so each one always has an `angle`. `from` is empty only for an idea of mine that doesn't build on any inbox day.
* `posts` hold one entry per LinkedIn post:
  * `date` and `topic` match the post's heading in [linkedin_posts.md](../output/linkedin_posts.md) exactly: `## YYYY-MM-DD · Topic`. The dashboard links to that heading, so if they differ, the link won't land on the post.
  * `from` lists the inbox days the post used, or is empty for a post that didn't come from the inbox, like a past post from setup.
  * `angle` is the `id` of the angle the post fits best.
  * `status` is `draft` until I approve the post, then `approved`.
  * `posted` is the day it went out on LinkedIn, or `null`.
  * `url` is the post's LinkedIn link, or `null`. `impressions` and `engagements` are its numbers from the latest export, or `null` until it has some. The dashboard shows only impressions, quietly; engagements are for your stats reply and topic picks.
  * `x` is the X version, or `null`. `format` is `post`, `thread`, or `article`. An article also has `file`, its file name in `output/x_articles/`. Posts and threads need nothing more, because their heading in [x_posts.md](../output/x_posts.md) is the same as the LinkedIn post's.
* Past posts I gave you are already out: use the day I posted them for both `date` and `posted`. If I didn't say when, leave them off the dashboard. Their numbers come with the next export.

## Size

The dashboard holds up to 500 KB and 20,000 values. A day's summary is small, so that's many years of days and posts. If it gets close, move the oldest year's days and posts to `assets/archive-<year>.json` and tell me. The day files in `inbox/` stay where they are.
