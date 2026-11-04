# My first month sending PRs into other people's code

A few weeks ago I stopped only building my own stuff and started sending pull requests into other people's codebases.

I didn't pick one project. I went wide: a command-line tool, an AI model verification tool, a healthcare app's frontend, a data library. Different languages, different maintainers, different ways of reviewing code.

Some of what I sent in were small cleanups, like a duplicate entry in a YAML export or a sort order that didn't match the rest of the file. A few mattered more than they look. One was a verifier that silently passed when it should have failed, because a hash was missing, which meant an unverified model could pass as verified.

Four got merged. The rest are open, waiting on review, or need another round.

The code wasn't the hard part. The hard part was that "done" means something different in someone else's project. In my own repos, I merge when it works. Here, working is the starting bar, not the finish line.

I'm not done with this. I'm going to keep sending PRs, and I'll keep posting what I find.
