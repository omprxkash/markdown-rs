# Git — Beyond the Basics

Git tracks the history of a project. Every commit is a snapshot you can go back to. Most people know `git add`, `git commit`, `git push`. What separates confident Git users from beginners is knowing how to use commits intentionally, how to design a branching structure, and what to do when things go wrong.

---

## The Perfect Commit

A commit should contain changes from a single topic. One bug fix, one feature, one refactor — not everything you did this afternoon mixed together.

**Why this matters:** the bigger and more mixed a commit, the harder it is to understand six months later. A clean commit history is documentation.

**Staging selectively** — `git add filename` adds an entire file. `git add -p filename` drops into **patch mode**, which steps through each chunk of changes and asks whether to include it. This lets you add part of a file to one commit and the rest to another.

**Commit messages** — two parts: a short subject line (under 80 characters) and an optional body separated by a blank line.

The subject: a brief summary of what changed.
The body: why it changed, what's different from before, anything to watch out for.

```
Add capture for email signup

Previous form had no server-side validation. Added required field
check on name and email before writing to the database. Returns
400 with field-specific error message if validation fails.
```

A subject you struggle to keep short is a sign the commit is too broad.

---

## Branching Strategies

Git gives you the tool. How you use it is up to you and your team. That means you need a written convention — otherwise every person works differently, conflicts multiply, and onboarding new people becomes painful.

**Two types of branches:**

**Long-running branches** — exist for the entire lifetime of the project. `main` or `master` is always one. Teams often have others: `develop`, `staging`, `production`. These represent states in your release process. The convention is usually: never commit directly to these. Code arrives on long-running branches through merges or rebases only.

**Short-lived branches** — created for a specific purpose (feature, bug fix, experiment) and deleted after being merged. They branch off a long-running branch and merge back into one.

**Two common strategies:**

**GitHub Flow** — one long-running branch (`main`), everything else is a short-lived branch. Simple, lean, good for teams that ship frequently.

**Git Flow** — `main` reflects production. `develop` is where feature branches merge. Release branches are cut from `develop`, tested, then merged into `main` with a version tag. More structure, more steps, better for teams with scheduled releases.

Most teams land somewhere between the two. The important thing is that it is written down.

---

## Pull Requests

Pull requests are not a Git feature — they are provided by your hosting platform (GitHub, GitLab, Bitbucket). The concept is the same everywhere.

**What they are:** a way to ask for code review before merging. Instead of merging directly into `main`, you open a PR, invite teammates to read the code and leave comments, then someone approves and merges.

**Why use them:** complex or important changes benefit from a second pair of eyes. PRs also create a written record of why something changed.

**Contributing to projects you do not own:** if you want to change code in a repository you cannot push to (like an open source project), you:
1. **Fork** the repo — creates your own personal copy
2. Make changes in a branch on your fork
3. Open a pull request proposing those changes be merged into the original

Pull requests are always based on branches, not individual commits.

---

## Merge Conflicts

A merge conflict happens when two branches made different changes to the same part of the same file and Git cannot automatically decide which one wins. The classic case: the same line was edited differently on two branches.

**Git will always tell you** — it prints the conflict immediately and lists unresolved files in `git status` under "unmerged paths." You cannot accidentally miss a conflict.

**What a conflict looks like inside the file:**

```
<<<<<<< HEAD
  <li>Contact us</li>
=======
  (deleted)
>>>>>>> develop
```

The section between `<<<<<<` and `=======` is what your current branch has. The section between `=======` and `>>>>>>>` is what the other branch has. You edit the file until it contains exactly what you want — removing the markers, keeping the right content, possibly combining both.

After fixing all conflicted files, stage them and commit. That commit signals to Git that the conflict is resolved.

**You can always abort** — if you get halfway through resolving and realise you are on the wrong track, `git merge --abort` returns everything to the state before the merge started. You cannot break anything you cannot undo.

---

## Merge vs Rebase

Both integrate changes from one branch into another. The difference is in the resulting history.

**Merge** — Git finds the common ancestor commit of both branches and creates a new **merge commit** that ties the two together. The full history of both branches is preserved. The downside is that the history shows the fork and the reconnection, which some find noisy.

**Fast-forward merge** — if one branch has no new commits since the fork point, Git can just move the pointer forward without creating a merge commit at all. This only works when the branch being merged into has not moved since the fork.

**Rebase** — instead of creating a merge commit, rebase replays your commits on top of another branch. The result looks like development happened in a straight line — no merge commit, no visible fork.

Under the hood, rebase removes your commits temporarily, applies the commits from the other branch, then replays your commits on top with new commit hashes. This is why **rebase rewrites history**.

**The golden rule:** never rebase commits that have already been pushed to a shared repository. Other people may have based work on those commits. Rewriting them breaks that link.

Rebase is for cleaning up your local history — for example, tidying up a feature branch before you integrate it into the team branch. Once commits are pushed and shared, use merge.
