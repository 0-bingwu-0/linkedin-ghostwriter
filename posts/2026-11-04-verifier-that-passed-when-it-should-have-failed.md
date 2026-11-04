# The verifier that passed when it should have failed

This is the first of three examples from my first month of open-source PRs, where "done" meant something different from what I was used to.

One project I contributed to checks AI models before they're used: is this model really the one it claims to be? Part of that is comparing a hash of the model file with the one on record.

I found a case where the hash on record was missing. Instead of failing, the check passed. So a model nobody had verified could show up as verified.

The fix was a few lines. What took longer was everything around it. The maintainer asked for a test showing the old behavior was wrong, and for the error to go through the project's own error handling, not a new check I'd bolted on.

In my own repo, I'd have changed the line and moved on. Here, the line was the easy part. It got merged after two rounds of review.
