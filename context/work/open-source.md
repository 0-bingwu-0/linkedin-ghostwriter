# Open source

Sending pull requests into other people's codebases.

Below is an example setup. Say "Set me up." in Chat to replace it with yours, or edit it directly.

## Overview

As of 2026-11-04, about a month in. I went wide instead of picking one project: a command-line tool, an AI model verification tool, a healthcare app's frontend, and a data library. Different languages, different maintainers, different ways of reviewing code.

Four PRs merged. The rest are open, waiting on review, or need another round. Some were small cleanups; a few mattered more than they look.

## AI model verification tool

Checks that a model is the one it claims to be before it's used, partly by comparing a hash of the model file with the one on record.

* The verifier silently passed when it should have failed, because the hash on record was missing. An unverified model could pass as verified.
* The fix was a few lines. The maintainer asked for a test showing the old behavior was wrong, and for the error to go through the project's own error handling instead of a new check. That took longer than the fix.
* Merged after two rounds of review.

## Data library

* First PR: a sort order that didn't match the rest of the file. Twenty minutes to write, two days to get a review.
* The maintainer asked me to split a bigger PR in two. The smaller half was merged the same afternoon.

## Healthcare app frontend

* Getting it running locally took two hours. I wrote the steps down as I went and opened a docs PR with them.

## Not tied to a project yet

* A duplicate entry in a YAML export. A small cleanup.
