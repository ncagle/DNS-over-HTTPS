*This is a page for cURL team members who have push access. It is mainly intended for new members to outline some of the once unwritten guidelines of the curl repo.*

## Add curl/curl as a remote in your local repo
Your github account should have a fork of the curl repository, and you have cloned that fork locally. In your clone you will have a remote --typically named 'origin'-- that points to your fork. You will need to add a remote --typically named 'upstream'-- that points to this canonical repo:

~~~
git remote add upstream git@github.com:curl/curl.git
~~~
Now if you run `git remote -v` you should have at least an origin and upstream:
~~~
origin  git@github.com:jay/curl.git (fetch)
origin  git@github.com:jay/curl.git (push)
upstream        git@github.com:curl/curl.git (fetch)
upstream        git@github.com:curl/curl.git (push)
~~~

##  Do not work in your local master branch

master should reflect upstream/master or what it is about to become once you push. If you work from your local master you could you end up accidentally pushing something you didn't intend to. Branches are cheap in git, work from topic branches to make changes.

## No merge commits on master

We use a linear history, do not push merge commits on master. Instead, when you are done with your work checkout your topic branch and rebase on upstream/master after fetching the latest changes.

## You are the Committer of *anything* you push

The person who did the work in a commit must be set in that commit as the *Author*. The person who pushes that commit to the repo must be set in that commit as the *Committer*. In this way you take responsibility for what you commit.

## Squash trivial commits

Commits that are all the same area and change should be squashed before you push. A scenario where this might happen is a PR associated branch updated by adding more commits instead of updating their original commit. For example, a poster may point out a typo or some other problem and as the owner fixes those problems they add more commits.

Before:
~~~
http2: handle closed streams when uploading
http2: typo
http2: show info message when stream closed
~~~

After:
~~~
http2: handle closed streams when uploading
~~~

## Run checksrc

We have a [coding style](https://github.com/curl/curl/blob/master/docs/CODE_STYLE.md) that must be followed. checksrc enforces a lot of that style, and you should run it before you push. On Windows you may instead run checksrc.bat from the command prompt as long as you do it from the projects directory (cd projects && checksrc).

## Commit style -- it's not a suggestion

Read the [CONTRIBUTE](https://github.com/curl/curl/blob/master/docs/CONTRIBUTE.md) document if you haven't already! There's a section in it on writing [good commit messages](https://github.com/curl/curl/blob/master/docs/CONTRIBUTE.md#write-good-commit-messages) that must be followed. Notably, not everyone's git editor wraps commit messages. For example I use gitk and if a commit message is one long line it's not wrapped and I can't easily read it. You must wrap the message at 72 with some rare exceptions like URLs, shell commands that shouldn't be broken up, etc. The subject _ideally_ should be less than 60 columns but we don't strictly enforce that.

Commit messages should be in imperative style present tense.

Yes:
~~~
nss: work around race condition in PK11_FindSlotByName()
~~~

No:
~~~
nss: worked around race condition in PK11_FindSlotByName()
~~~

Also see [A Note About Git Commit Messages](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)

## How to work with a PR branch

Using all you've learned above, let's say you want to commit PR 239. First name it as local branch pr_239, then check out a temporary branch from that and rebase on upstream/master.
~~~
# First sure your index is clean.
git diff-index --quiet --cached HEAD || echo "WARNING: INDEX ISN'T CLEAN"

C=239;git fetch upstream refs/pull/$C/head:pr_$C
git checkout -b temp pr_$C
git fetch upstream && git rebase upstream/master
~~~

Count the number of commits. If there is a single commit, regardless of whether the message needs to be modified you need to amend the commit to become the committer.
~~~
git commit --amend -c HEAD
~~~

If however let's say there are 3 commits we want to squash them into one. To do that we'll soft reset back to their 1st commit which will move the changes from the later two commits to the index. Then append to the first commit. (You could instead use `git rebase -i` and choose what you want to squash.) Otherwise if there is not more than a single commit skip these steps.
~~~
git reset --soft HEAD~2
git commit --amend
~~~

Modify the commit message to meet guidelines. At the very least you will want to add a Bug: line or Fixes (etc. **TODO explain this better**). Examples: [3a5d5de](https://github.com/curl/curl/commit/3a5d5de)

Confirm that you ARE listed as the committer and ARE NOT listed as the author. git gui in particular will amend commits in a way that you can be listed as the author for someone else's work, likely not what you intended. Fix any error, for example `git commit --amend --author="who <who@is.this>"`.

Once you are ready, and you have met all of the guidelines discussed here, merge into your local master using fast-forward merge only, so there will not be a merge commit. If this step fails, master has some commit that is not in upstream/master (note earlier guideline don't work in master).
~~~
git checkout master
git merge --ff-only temp
~~~

Check once again to make sure master looks the way you expect it to look, and then push upstream.
~~~
git push upstream
~~~

## How to work with an issue
When you write a fix for an issue it's best to do it in a local branch that you push to your origin, not upstream. Then share that branch in the thread so that other people can comment on it and the reporter can try your fix. Make sure in your commit you reference the issue as `Bug:` and the reporter in `Reported-by:`. Use the reporter's real name if known (go to their user page). If not known use `username@users.noreply.github.com`. See [issue 983](https://github.com/curl/curl/issues/983#issuecomment-242625063) for an example. After others confirm the fix you will need to follow steps similar to the PR steps.

~~~
git checkout -b temp disable_schannel_alpn_wine
git fetch upstream && git rebase upstream/master
git checkout master
git merge --ff-only temp
# Make certain the changes reflect what you want to go upstream, then send it
git push upstream
git branch -D temp
~~~

The result in this case is [895168b](https://github.com/curl/curl/commit/895168b)
