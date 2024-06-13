## Amend

Amend the last commit with new changes. This helped me when I had some basic whitespace changes that didn't warrant a new commit. Giving the --no-edit option means we won't edit the commit message.

```bash
git commit --amend --no-edit
```

## Fixup

Combine the last commit with the previous commit.

```bash
git commit --fixup <commit>
```

## Reword

Change the commit message of the last commit.

```bash
git rebase -i HEAD~2 # operate on the last two commits
```

```bash
pick 1a2b3c4 Last commit
reword 5d6e7f8 Previous commit # change the commit message
reword 9g0h1i2 Commit 1 # change the commit message

# Commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
```

## Squash & Fixup

Squash and fixup allow us to combine multiple commits into one. We can mark commits as `fixup` or `squash` in an interactive rebase, and squash will prompt for a new commit message whereas fixup will use the previous commit message. One of the conventions at a job I had was to only have a single commit per pull request, so I would use this to combine all my commits into one before merging.

When I first used this with I had to use a `git push --force` on Bitbucket to update the remote repository.

```bash
git rebase -i HEAD~2 # operate on the last two commits
```

### With Fixup

```bash
pick 1a2b3c4 Last commit
fixup 5d6e7f8 Previous commit # gets squashed into 'Last commit'
fixup 9g0h1i2 Commit 1 # gets squashed into 'Last commit'

# Commands:
# p, pick = use commit
# f, fixup = like "squash", but discard this commit's log message
```

### With Squash

```bash
pick 1a2b3c4 Last commit
squash 5d6e7f8 Previous commit # gets squashed into 'Last commit'
squash 9g0h1i2 Commit 1 # gets squashed into 'Last commit'

# Commands:
# p, pick = use commit
# s, squash = use commit, but meld into previous commit
```

## Resetting to fix my booboos

Sometimes I need to reverse through my commit history to fix a mistake I've made.

### Soft

Undoes all of the changes between HEAD and the commit, but leaves the changes staged.

```bash
git reset --soft HEAD~1
```

### Mixed

Undoes all of the changes between HEAD and the commit, but leaves the changes unstaged.

```bash
git reset --mixed HEAD~1
```

### Hard

Undoes all of the changes between HEAD and the commit, and discards the changes.

```bash
git reset --hard HEAD~1
```

## Finding Commits

We can find all of the commits for a given file by using the `--follow` option.

```bash
git log --follow --oneline -- filename
```
