# Contributing to linux-starters

We are big fans of linear commit histories so only changes that can fast-forwarded will be allowed. This is easy to achieve with a solo maintainer.
```
git config --global merge.ff only
git config --global pull.ff only
```
The way we currently manage versioning is by having 3 release candidates every season run - to coincide with the 3 weeks, e.g. `v0.6-rc1` to refer to week 1 of season 6's run. These are only merged after the conclusion of the class and post-mortem review - which happens anywhere in the week.

Each `rc` cycle goes through 3 phases:
1. Starts with a PR opened with changes from the previous week, e.g. `W1` (explained later)
1. Development/changes by the current week's maintainer, e.g. `W2` - of which the content is ready for pre-class vetting/dry-run by a maintainer.
1. Changes are then squashed and PR-ed
1. 

<!-- Two or three sentences, max. What the repo is, who it's for, and the one
     thing a stranger needs to understand before reading further — that this
     material is taught live to first-time shell users.
     Do not put rules here. This is orientation only. -->

## Code of Conduct

<!-- One line + a link to CODE_OF_CONDUCT.md. Do not inline the text.
     If you don't have one yet, this section is a stub with a TODO — an empty
     header is more honest than a missing one. -->

## How can I contribute?

<!-- The menu. Four or five bullets, each linking down to its own section:
       - Report something that broke in a session
       - Report a bug in the tooling
       - Propose new or revised material
       - Improve docs
       - Facilitate and feed back
     Name the label a newcomer should filter on. -->

## Reporting problems

<!-- Split this if the two kinds diverge enough:
       - Broke in the room: which cohort, which week, what the learner saw,
         what was on screen. Screenshot from the actual machine.
       - Tooling bug: target hardware, command run, expected vs actual.
     Link the issue templates rather than restating the fields. -->

## Proposing new material

<!-- Where to raise it before building it, and what happens next.
     State the bar: does new material need a facilitator sponsor? Does it need
     to be dry-run before the PR? Answer it here so nobody guesses. -->

## Development setup

<!-- Clone, dependencies, how to render a deck locally, how to reach the
     classroom target. Assume competence, not familiarity — the reader knows
     Linux, they don't know your repo.
     If setup differs on x86 vs the Pi fleet, say so here. -->

## Making changes

<!-- Branch naming, commit convention, and a link to STYLE.md.
     Do NOT restate the style guide here. One line pointing at it, and a
     sentence saying that content changes are held to it. -->

## Verifying your change

<!-- The pre-PR checklist. Split content vs tooling — they have different bars.
     The non-negotiable one: rendered on the actual classroom target, with
     evidence in the PR. Say what counts as evidence. -->

## Contributing from a learner fork

<!-- The second journey. Someone finished a cohort, fixed something in their
     fork, wants it upstream. Cover: syncing a stale fork, that they branch off
     upstream main not their own, and that the bar is the same as anyone else's.
     Keep it warm. This is the path you most want people to actually walk. -->

## Pull requests

<!-- What the title must look like (it becomes the squash-merge commit message).
     What the body must answer. How many approvals, who merges, what CI gates
     the merge. That the author doesn't merge their own.
     One line on review tone. -->

## Never commit

<!-- Learner PII, photos, attendance data, keys, real SITTER values, anything
     from a signup booth event, .env, device addresses.
     Say what to do if it happens anyway — disclosing fast must be the obvious
     move, not the frightening one. -->

## Releases and versioning

Over here we follow a simple Semver. 4 commits a season and a tag every season run conclusion (after review)

Use `git switch` over `checkout`. Git `2.23` (2019) introduced `switch` and `restore` to target branches and files respectively.

To fetch repo tags:  
`git fetch origin tag archive/pre-day-zero`

and then check the fetched releases tags:  
`git tag -l`

git stash your changes:  
`git add . && git stash`  

Use git switch to check detached branches:  
`git switch --detach archive/pre-day-zero`

Switch back:
`git switch - `


## Becoming a maintainer

<!-- The path, and what maintainership actually is (the duty to read other
     people's work carefully). Link MAINTAINERS.md. -->

## License

<!-- What terms contributions land under. State whether you require a DCO
     sign-off. If you do, this section must show the exact `git commit -s`
     invocation, because that's where people get stuck. -->