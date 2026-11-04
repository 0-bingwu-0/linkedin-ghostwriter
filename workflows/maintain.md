# Keep the Dashboard Current

The dashboard is `index.html`: my ideas waiting to be written, my drafts waiting to go out, and what I've posted. Everything it shows comes from `assets/posts.json`, and keeping that file current is your job. The posts themselves stay in `posts/`, one file each; the JSON only lists them, and the dashboard links to each file. StashBase shows your changes within a couple of seconds, even while the dashboard is open.

I can do two things on the dashboard myself: mark a draft posted, or take it back, and drop an idea. The page saves those to the same file.

## When to update it

* **When I tell you an idea:** add it to the top of `ideas`, as in [idea.md](idea.md). If it builds on one already there, update that one instead.
* **When I say how I'd tell it:** put it in the idea's `plan`, in a few words.
* **When an idea turns into a series:** set its `series` to `true`, write the posts in it into `plan`, and set `series` on any posts already written for it.
* **After writing a post:** add it to `posts` as a draft, as in [write.md](write.md#saving). Then suggest removing the idea it came from, and remove it if I agree. For a series, update the plan instead, and suggest removing the idea once its last post is written.
* **When I tell you I posted one:** set its `posted` to today, unless I say another day.
* **When I drop an idea:** remove it.
* **When a post's file is added, renamed, or gone,** or its title changes: update its entry.
* **At setup:** replace the example, as in [setup.md](setup.md).

## Editing rules

* Read the file right before you change it. I may have marked a post or dropped an idea on the dashboard since you last looked, and my changes stay.
* Keep it valid JSON. Change only what you need, and leave every other field as it is, including fields not listed here.
* Dates are `YYYY-MM-DD`.
* Don't change `schemaVersion` or `index.html`.

## Format

```json
{
  "example": true,
  "ideas": [
    { "date": "2026-11-04", "idea": "Done means something different in someone else's project", "series": true, "plan": "An intro, three examples, one per post, and a wrap-up." },
    { "date": "2026-11-02", "idea": "Reading a stranger's codebase is a skill nobody teaches", "plan": "" }
  ],
  "posts": [
    { "date": "2026-11-04", "title": "My first month sending PRs into other people's code", "file": "2026-11-04-first-month-sending-prs.md", "series": "Done means something different in someone else's project", "posted": "2026-11-04" }
  ]
}
```

* `example` is `true` only while the template's example is in place; the dashboard then also tells people to say "Set me up." Setup removes it.
* `ideas` are my ideas waiting to be written, newest first.
  * `date` is the day it was added. `idea` is the idea, close to my words.
  * `plan` is how I'd tell it, or for a series, the posts in it and what's still open. Leave it empty until I've said.
  * `series` is `true` for a series. A series stays here until its last post is written.
* `posts` are my posts, past and new, newest first.
  * `date` is the date in its file name, or `null` for a past post with no date in its name.
  * `title` is the `#` heading in its file. `file` is its file name in `posts/`.
  * `series` is the `idea` of the series it's part of. Leave it out otherwise.
  * `posted` is the day it went out, `true` if it went out but I don't know the day, or `null` while it's a draft. Past posts I give you are posted.

## Size

The dashboard holds up to 500 KB and 20,000 values. Each idea and post is one short entry, so that's thousands of them. If it ever gets close, move the oldest posted posts to `assets/archive-<year>.json` and tell me. Their files stay in `posts/`.
