# Find Topics

If I already gave you a topic, skip this and go to [write.md](write.md).

## Start from my work

When I ask what to post without giving a topic, ask me one question first: what have I been working on or learning lately? A sentence or two is enough, like something I built, a problem I solved, or a call I made.

If I share something, follow [Pick topics](#pick-topics) and skip "What's hot." If I have nothing, or I ask for what's hot, go to [Find what's hot](#find-whats-hot).

## Find what's hot

Only look at posts from the last 24 hours by the X accounts below (example accounts; replace them with sources in your field). Don't search anywhere else. Run this once from the project root, and tell me the estimated cost the script prints at the end:

```bash
node workflows/scripts/x-search.mjs 24 TheRundownAI karpathy simonw emollick
```

| Account | What to watch for |
| --- | --- |
| @TheRundownAI | Daily roundup of confirmed AI news |
| @karpathy | How models work, explained from the ground up |
| @simonw | Hands-on notes on new models and tools |
| @emollick | How AI is actually used at work and in education |

When changing accounts, update both the table and the command. Don't save the raw results.

If the script says `X_BEARER_TOKEN` isn't set, don't look for other sources. Ask me which way I want to go:

1. **Set up the X API** to pull fresh posts. Walk me through the setup in the [README](../README.md#x-api), then run it again.
2. **Start from a post I give you.** I paste a post I came across (its text, plus the link if I have it), and you use it as the topic. See [Start from a post](#start-from-a-post).
3. **Skip the feed.** Suggest topics from my profile and past posts alone. See [Pick topics](#pick-topics), and leave out "What's hot."

## Start from a post

When I give you a post instead of a feed, skip "What's hot." Use what I pasted. If I only gave a link and you can't open it, ask me to paste the text. Then follow the steps in [Pick topics](#pick-topics), with one change: replace "What's hot" with a one-line summary of the post, and make each suggested topic my own take on the same subject.

## Pick topics

First read [profile.md](../context/profile.md) and the recent posts in [linkedin_posts.md](../output/linkedin_posts.md). Then reply like we're chatting, in two parts:

1. **What's hot:** Group posts by story and rank stories by how relevant they are to my background and posting angle. Give each one a sentence or two with the original link. Mark leaks and single-source claims as unconfirmed.
2. **Suggested topics:** Two or three. For each, a short paragraph: how I could tell it, why people I want to reach would care, and what from my work or views it connects to. Use the "Posting angle" in my profile. When a topic would be much stronger with a story from my work, say what kind of story would fit, and I'll tell you if I have one. Avoid repeating recent content. Building on an earlier topic is even better.
