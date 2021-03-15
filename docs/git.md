# Git

* [On undoing, fixing, or removing commits in git](https://sethrobertson.github.io/GitFixUm/fixup.html)
* [Useful commands](http://orga.cat/posts/most-useful-git-commands)
* [Clean-up outdated branches](http://railsware.com/blog/2014/08/11/git-housekeeping-tutorial-clean-up-outdated-branches-in-local-and-remote-repositories/)

---

## Initialize a repo

```
git init
git add .
git commit -m 'Initial import.'
git remote add origin ${URL}
git push --set-upstream origin master
```

## Show commit log with branches and tags

```
$ git log --graph --all --decorate
```

## Create a patch

```
git diff --patch-with-raw > out.patch
git diff HEAD~1 --relative

```

## Fetch changes from origin/master without checking out master

[Git alias](https://github.com/andornaut/dotfiles/blob/dd397e2966df7ba97b7b2043020bdd958d32f0a3/%24HOME/.config/git/config#L15)

```
git checkout --detach --quiet HEAD && git fetch origin master:master && git checkout --quiet -
```

## Clean-up local branches
```
$ git branch --merged
$ git branch -d merged-branch-name
$ git branch --no-merged
$ git branch -D un-merged-branch-name
```

## Prune tracking branches
```
$ git branch -r
$ git remote prune origin
# Or just fetch with -p
$ git fetch -p
```

## List merged branches on origin
```
$ for branch in `git branch -r --merged | grep -v HEAD`; do \
	echo -e `git show --format="%ci %cr %an" $branch | head -n 1` \\t$branch; \
done | sort -r
```

## See commit history for the last two commits, including the diff
```
git log -p -2
```

## Squash all but first commit
```
$ git rebase -i $(git rev-list --max-parents=0 HEAD)
# Change all but the first "pick" to "squash"
$ git push --force
```

## Pull a --force pushed branch
```
git fetch
git reset origin/master --hard
```

## Change origin URL
```
$ git remote set-url origin git://$URL
```

## Configuration
```
# Project-specific
$ git config user.name "andornaut" \
    && git config user.user "andornaut" \
    && git config user.email "andornaut@users.noreply.github.com"
```

## Convert a mercurial repo to git

[hg-fast-export](https://github.com/frej/fast-export)

```
mkdir repo-git
cd repo-git
git init
hg-fast-export.sh -r <repo> -B <branches_map> -A <users_map>
```

## Ignore/unignore changes to a file

```
# Ignore
git update-index --assume-unchanged ${filepath}

# Unignore
git update-index --no-assume-unchanged ${filepath}
```

## Delete tag

```
git tag -d v0.0.1
git push origin :refs/tags/v0.0.1
```

## Github

### Collapsable section markdown

* [Gist](https://gist.github.com/joyrexus/16041f2426450e73f5df9391f7f7ae5f)

```
<details><summary>Click here to expand</summary>

This section is hidden until the above is clicked.
</details>
```

### Search

* [GitHub searching-issues-and-pull-requests](https://docs.github.com/en/github/searching-for-information-on-github/searching-issues-and-pull-requests)
* [GitHub using-search-to-filter-issues-and-pull-requests](https://docs.github.com/en/github/managing-your-work-on-github/using-search-to-filter-issues-and-pull-requests)


```
is:pr,issue
is:closed 
author:andornaut 
archived:false 
org:ORGNAME
reviewed-by:andornaut
```
