# Awesome git addons [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

A curated list of addons that extends git cli.

```
$ git bla
Something awesome happens!
```

Inspired by the [awesome](https://github.com/sindresorhus/awesome) list thing.


## Table of Contents

- [Git Extras](#git-extras)
- [Git Flow](#gitflow-avh-edition)
- [Git Up](#git-up)
- [Hub](#hub)
- [Git Deploy](#git-deploy)
- [Git Cal](#git-cal)
- [Git Hooks](#git-hooks)
- [Git Imerge](#git-imerge)
- [Git Large File Storage](#git-lfs)
- [Git Now](#git-now)
- [Git Plus](#git-plus)
- [Git Test](#git-test)
- [Legit](#legit)


## [git-extras](https://github.com/tj/git-extras)

### squash

```
$ git squash fixed-cursor-styling "Fixed cursor styling"
$ git squash 95b7c52
$ git squash HEAD~3
```

### summary

```
$ git summary

 project  : git
 repo age : 10 years
 active   : 11868 days
 commits  : 40530
 files    : 2825
 authors  :
 15401	Junio C Hamano                  38.0%
  1844	Jeff King                       4.5%
```

### line-summary

```
$ git line-summary

 project  : gulp
 lines    : 3900
 authors  :
 1040 Contra                    26.7%
  828 Sindre Sorhus             21.2%
```

### effort

```
$ git effort

  file                                          commits    active days

  .gitattributes............................... 3          3
  .gitignore................................... 265        226
  .mailmap..................................... 47         40
```

### authors

```
$ git authors
Contra <contra@maricopa.edu>
Eric Schoffstall <contra@wearefractal.com>
Sindre Sorhus <sindresorhus@gmail.com>
```

### changelog

```
$ git changelog
## 3.9.0

- add babel support
- add transpiler fallback support
- add support for some renamed transpilers (livescript, etc)
- add JSCS
- update dependecies (liftoff, interpret)
- documentation tweaks

## 3.8.11

- fix node 0.12/iojs problems
- add node 0.12 and iojs to travis
- update dependencies (liftoff, v8flags)
- documentation tweaks
```

### commits-since

```
$ git commits-since yesterday
... changes since yesterday
TJ Holowaychuk - Fixed readme
```

### count

```
$ git count
total 855
```

### create-branch

```
$ git create-branch development
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/tj/git-extras.git
 * [new branch]      HEAD -> development
Branch development set up to track remote branch development from origin.
Switched to a new branch 'development'
```

### delete-branch

```
$ git delete-branch integration
Deleted branch integration (was bfb8522).
Deleted remote-tracking branch remote/integration (was bfb8522).
To git@github.com:remote/gulp.git
 - [deleted]         integration
```

### delete-submodule

```
$ git delete-submodule lib/foo
```

### delete-tag

```
$ git delete-tag v0.1.1
Deleted tag 'v0.1.1' (was 9fde751)
To https://github.com/tj/git-extras.git
 - [deleted]         v0.1.1
```

### delete-merged-branches

```
$ git delete-merged-branches
Deleted feature/themes (was c029ab3).
Deleted feature/live_preview (was a81b002).
Deleted feature/dashboard (was 923befa).
```

### fresh-branch

```
$ git fresh-branch docs
Removing .DS_Store
Removing .editorconfig
Removing .gitignore
```

### guilt

```
$ git guilt `git log --until="3 weeks ago" --format="%H" -n 1` HEAD
Paul Schreiber                +++++++++++++++++++++++++++++++++++++++++++++(349)
spacewander                   +++++++++++++++++++++++++++++++++++++++++++++(113)
Mark Eissler                  ++++++++++++++++++++++++++
```

### merge-into

```
$ git merge-into master
Switched to branch 'master'
Your branch is up-to-date with 'origin/master'.
Updating 9fde751..e62edfa
Fast-forward
 234 | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 234
Switched to branch 'development'
```

### graft

```
$ git graft new_feature master
```

### alias

```
$ git alias last "cat-file commit HEAD"
$ git alias
last = cat-file commit HEAD
```

### ignore

```
$ git ignore build "*.o" "*.log"
... added 'build'
... added '*.o'
... added '*.log'
```

### info

```
$ git info

    ## Remote URLs:

    origin              git@github.com:sampleAuthor/git-extras.git (fetch)
    origin              git@github.com:sampleAuthor/git-extras.git (push)

    ## Remote Branches:

    origin/HEAD -> origin/master
    origin/myBranch

    ## Local Branches:

    myBranch
    * master

    ## Most Recent Commit:

    commit e3952df2c172c6f3eb533d8d0b1a6c77250769a7
    Author: Sample Author <sampleAuthor@gmail.com>

    Added git-info command.

    Type 'git log' for more commits, or 'git show <commit id>' for full commit details.

    ## Configuration (.git/config):

    color.diff=auto
    color.status=auto
```

### fork

```
$ git fork LearnBoost/expect.js
```

### release

```
$ git release 0.1.0
... releasing 0.1.0
On branch development
Your branch is up-to-date with 'origin/development'.
nothing to commit, working directory clean
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/tj/git-extras.git
   9fde751..e62edfa  master -> master
Counting objects: 1, done.
Writing objects: 100% (1/1), 166 bytes | 0 bytes/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To https://github.com/tj/git-extras.git
 * [new tag]         0.1.0 -> 0.1.0
... complete
```

### contrib

```
$ git contrib visionmedia
visionmedia (18):
  Export STATUS_CODES
  Replaced several Array.prototype.slice.call() calls with Array.prototype.unshift.call()
  Moved help msg to node-repl
```

### repl

```
$ git repl

git> ls-files
History.md
Makefile
```

### undo

```
$ git undo
Unstaged changes after reset:
M	package.json
M	readme.md
```

### gh-pages

```
$ git gh-pages
```

### scp

```
$ git scp staging HEAD
```

### setup

```
$ git setup
Initialized empty Git repository in /GitHub/test/gulp/.git/
[master (root-commit) 9469797] Initial commit
 69 files changed, 3900 insertions(+)
 create mode 100644 .editorconfig
 create mode 100644 .gitignore
 create mode 100644 .jscsrc
```

### touch

```
$ git touch index.js
```

### obliterate

```
$ git obliterate secrets.json
Rewrite 2357a4334051a6d1733037406ab7538255030d0b (1/981)rm 'secrets.json'
Rewrite b5f62b2746c23150917d346bd0c50c467f01eb03 (2/981)rm 'secrets.json'
Rewrite 3cd94f3395c2701848f6ff626a0a4f883d8a8433 (3/981)rm 'secrets.json'
```

### feature|refactor|bug|chore

```
$ git feature dependencies
$ git feature finish dependencies
Already up-to-date.
Deleted branch feature/dependencies (was f0fc4c7).
Deleted remote-tracking branch origin/feature/dependencies (was f0fc4c7).
To git@github.com:stevemao/gulp.git
 - [deleted]         feature/dependencies
```

### local-commits

```
$ git local-commits
commit 5f00a3c1bb71876ebdca059fac96b7185dea5467
Merge: 7ad3ef9 841af4e
Author: Blaine Bublitz <blaine@iceddev.com>
Date:   Thu Aug 20 11:35:15 2015 -0700

    Merge pull request #1211 from JimiHFord/patch-1

    Update guidelines.md

commit 841af4ee7aaf55b505354d0e86d7fb876d745e26
Author: Jimi Ford <JimiHFord@users.noreply.github.com>
Date:   Thu Aug 20 11:55:38 2015 -0400

    Update guidelines.md

    fixed typo
```

### archive-file

```
$ git archive-file
Building archive on branch "master"
Saved to "gulp.v3.9.0-36-g47cb6b0.zip" ( 60K)
```

### missing

```
$ git missing master
< d14b8f0 only on current checked out branch
> 97ef387 only on master
```

### lock

```
$ git lock config/database.yml
```

### locked

```
$ git locked
config/database.yml
```

### unlock

```
$ git unlock config/database.yml
```

### reset-file

```
$ git reset-file README.md HEAD^
Reset 'README.md' to HEAD^
```

### pr

```
$ git pr 226
From https://github.com/tj/git-extras
 * [new ref]       refs/pulls/226/head -> pr/226
Switched to branch 'pr/226'
```

### root

```
$ git root
/GitHub/git
```

### delta

```
$ git delta
README.md
```

### merge-repo

```
$ git merge-repo git@github.com:tj/git-extras.git master .
git fetch git@github.com:tj/git-extras.git master
warning: no common commits
remote: Counting objects: 3507, done.
remote: Compressing objects: 100% (5/5), done.
remote: Total 3507 (delta 1), reused 0 (delta 0), pack-reused 3502
Receiving objects: 100% (3507/3507), 821.12 KiB | 286.00 KiB/s, done.
Resolving deltas: 100% (1986/1986), done.
From github.com:tj/git-extras
 * branch            master     -> FETCH_HEAD
Added dir 'git-merge-repo.E95m0gj'
No local changes to save
```

### psykorebase

```
$ git psykorebase master
$ git psykorebase --continue
$ git psykorebase master feature
```


## [gitflow (AVH Edition)](https://github.com/petervanderdoes/gitflow)

### flow init

```
$ git flow init

Which branch should be used for bringing forth production releases?
   - changelog
   - master
Branch name for production releases: [master]

Which branch should be used for integration of the "next release"?
   - changelog
Branch name for "next release" development: [master]
Production and integration branches should differ.
```

### flow feature

```
$ git flow feature
$ git flow feature start awesome-feature
$ git flow feature finish awesome-feature
$ git flow feature delete awesome-feature

$ git flow feature publish awesome-feature
$ git flow feature pull remote awesome-feature
```

### flow release

```
$ git flow release
$ git flow release start awesome-release
$ git flow release finish awesome-release
$ git flow release delete awesome-release
```

### flow hotfix

```
$ git flow hotfix
$ git flow hotfix start awesome-release
$ git flow hotfix finish awesome-release
$ git flow hotfix delete awesome-release
```

### flow support

```
$ git flow support
```


## [git-up](https://github.com/aanand/git-up)

```
$ git up
Fetching origin
4.0       fast-forwarding...
changelog ahead of upstream
master    fast-forwarding...
returning to 4.0
```


## [hub](https://github.com/github/hub)

### clone

```
$ git clone schacon/ticgit
> git clone git://github.com/schacon/ticgit.git

$ git clone -p schacon/ticgit
> git clone git@github.com:schacon/ticgit.git

$ git clone resque
> git clone git@github.com/YOUR_USER/resque.git
```

### remote add

```
$ git remote add rtomayko
> git remote add rtomayko git://github.com/rtomayko/CURRENT_REPO.git

$ git remote add -p rtomayko
> git remote add rtomayko git@github.com:rtomayko/CURRENT_REPO.git

$ git remote add origin
> git remote add origin git://github.com/YOUR_USER/CURRENT_REPO.git
```

### fetch

```
$ git fetch mislav
> git remote add mislav git://github.com/mislav/REPO.git
> git fetch mislav

$ git fetch mislav,xoebus
> git remote add mislav ...
> git remote add xoebus ...
> git fetch --multiple mislav xoebus
```

### cherry-pick

```
$ git cherry-pick http://github.com/mislav/REPO/commit/SHA
> git remote add -f --no-tags mislav git://github.com/mislav/REPO.git
> git cherry-pick SHA

$ git cherry-pick mislav@SHA
> git remote add -f --no-tags mislav git://github.com/mislav/CURRENT_REPO.git
> git cherry-pick SHA

$ git cherry-pick mislav@SHA
> git fetch mislav
> git cherry-pick SHA
```

### am

```
$ git am https://github.com/defunkt/hub/pull/55
[ downloads patch via API ]
> git am /tmp/55.patch

$ git am --ignore-whitespace https://github.com/davidbalbert/hub/commit/fdb9921
[ downloads patch via API ]
> git am --ignore-whitespace /tmp/fdb9921.patch
```

### apply

```
$ git apply https://gist.github.com/8da7fb575debd88c54cf
[ downloads patch via API ]
> git apply /tmp/gist-8da7fb575debd88c54cf.txt
```

### fork

```
$ git fork
[ repo forked on GitHub ]
> git remote add -f YOUR_USER git@github.com:YOUR_USER/CURRENT_REPO.git
```

### pull-request

```
$ git pull-request
[ opens text editor to edit title & body for the request ]
[ opened pull request on GitHub for "YOUR_USER:feature" ]
```

### checkout

```
$ git checkout https://github.com/defunkt/hub/pull/73
> git remote add -f --no-tags -t feature mislav git://github.com/mislav/hub.git
> git checkout --track -B mislav-feature mislav/feature
```

### merge

```
$ git merge https://github.com/defunkt/hub/pull/73
> git fetch git://github.com/mislav/hub.git +refs/heads/feature:refs/remotes/mislav/feature
> git merge mislav/feature --no-ff -m 'Merge pull request #73 from mislav/feature...'
```

### create

```
$ git create
[ repo created on GitHub ]
> git remote add origin git@github.com:YOUR_USER/CURRENT_REPO.git
```

### init

```
$ git init -g
> git init
> git remote add origin git@github.com:YOUR_USER/REPO.git
```

### push

```
$ git push origin,staging,qa bert_timeout
> git push origin bert_timeout
> git push staging bert_timeout
> git push qa bert_timeout
```

### browse

```
$ git browse
> open https://github.com/YOUR_USER/CURRENT_REPO
```

### compare

```
$ git compare refactor
> open https://github.com/CURRENT_REPO/compare/refactor
```

### submodule

```
$ git submodule add wycats/bundler vendor/bundler
> git submodule add git://github.com/wycats/bundler.git vendor/bundler
```

### ci-status

```
$ git ci-status
success
```


## [git-deploy](https://github.com/mislav/git-deploy)

```
$ git remote add production "user@example.com:/apps/mynewapp"
$ git deploy setup -r "production"
$ git deploy init
$ git push production master
```


## [git-cal](https://github.com/k4rthik/git-cal)

```
$ git cal
    Aug   Sep     Oct     Nov       Dec     Jan       Feb     Mar     Apr     May       Jun     Jul     Aug
        ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼
    M   ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼
        ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼
    W ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼
      ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼
    F ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼
      ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼ ◼

                                                                                               Less ◼ ◼ ◼ ◼ ◼  More
1907: Total commits
  78: Days ( Apr 15 2015 - Jul  5 2015 ) - Longest streak excluding weekends
  35: Days ( May 17 2015 - Jun 20 2015 ) - Longest streak including weekends
   0: Days - Current streak
```


## [git-hooks](https://github.com/icefox/git-hooks)


## [git-imerge](https://github.com/mhagger/git-imerge)

### imerge start

### imerge merge

```
$ git imerge merge 4.0
Attempting automerge of 1-1...success.
Attempting automerge of 1-6...success.
Attempting automerge of 1-9...success.
Attempting automerge of 1-10...success.
```

### imerge rebase

```
$ git imerge rebase 4.0
The following commits on the to-be-merged branch are merge commits:
    8e4931ae15971a14897cf347ac50b7d7fe125ac4
    d7c772142ce663a20210db73d9ad17cc8d59e0d6
    856df83c77b33029d2ddfb8eecd08efedeadc027
```

### imerge continue

### imerge finish

### imerge diagram

### imerge list

### imerge init

### imerge record

### imerge autofill

### imerge simplify

### imerge remove

### imerge reparent


## [git-lfs](https://github.com/github/git-lfs)


## [git-now](https://github.com/iwata/git-now)

```
$ git now
[master 1bd9ce8] [from now] 2015/08/27 10:39:10
 1 file changed, 1 insertion(+), 1 deletion(-)
$ git log
commit 1bd9ce878a76140f7db95afd9cfd4d7befbc7243
Author: Steve Mao <maochenyan@gmail.com>
Date:   Thu Aug 27 10:39:10 2015 +1000

    [from now] 2015/08/27 10:39:10

    diff --git a/package.json b/package.json
    index 8768569..540523a 100644
    --- a/package.json
    +++ b/package.json
    @@ -1,7 +1,7 @@
     {
       "name": "gulp",
       "description": "The streaming build system",
    -  "version": "3.9.0",
    +  "version": "3.10.0",
       "homepage": "http://gulpjs.com",
       "repository": "gulpjs/gulp",
       "author": "Fractal <contact@wearefractal.com> (http://wearefractal.com/)",
```


## [git-plus](https://github.com/tkrajina/git-plus)

### multi

```
$ git multi
--------------------------------------------------------------------------------
Executing git status -s
--------------------------------------------------------------------------------
chalk:
	 M package.json

gulp:
	 D index.js
```

### relation

```
$ git relation origin/4.0
HEAD and origin/4.0 DIVERGED, common point is 657213a52d5e9c19b85df6a42f76341a98c08ae8

Commits from 657213a52d5e9c19b85df6a42f76341a98c08ae8 to HEAD:
Error retrieving log 657213a52d5e9c19b85df6a42f76341a98c08ae8..HEAD
```

### old-branches

```
$ git old-branches -d 10
Branch 4.0 is older than 10 days (139.86)!
```


## [git-test](https://github.com/spotify/git-test)

```
$ git test -v
4.0 ^origin/4.0 ^origin/master will test        2 commits
iter commit  tree    result
0000 57af4b0 f5ef0d8 pass (cached)
0001 10ed389 434370f pass
```


## [legit](https://github.com/kennethreitz/legit)

### branches

```
$ git branches
   4.0                        (published)
   development                (unpublished)
   everything-is-not-awesome  (published)
*  master                     (published)
   old-master                 (published)
```

### sync

```
$ git sync
Pulling commits from the server.
First, rewinding head to replay your work on top of it...
Fast-forwarded 4.0 to origin/4.0.
Pushing commits to the server.
```

### resync

```
$ git resync
Switching to master.
Your branch is ahead of 'origin/master' by 10 commits.
  (use "git push" to publish your local commits)
Pulling commits from the server.
Already up-to-date.
Switching to master.
Your branch is ahead of 'origin/master' by 10 commits.
  (use "git push" to publish your local commits)
Grafting commits from master.
Already up-to-date.
Pulling commits from the server.
Already up-to-date.
Pushing commits to the server.
```

### switch

```
$ git switch master
Saving local changes.
Saved working directory and index state On developement: Legit: stashing before switching branches.
HEAD is now at f0fc4c7 Merge branch 'development'
Switching to master.
Your branch is up-to-date with 'origin/master'.
Restoring local changes.
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   package.json

no changes added to commit (use "git add" and/or "git commit -a")
Dropped stash@{0} (86f5dc9066ff9f69c01c77e2f5a55643ad19f8f2)
```

### sprout

```
$ git sprout development
Branching master to development.
```

### harvest

```
$ git harvest development
Grafting commits from development.
Updating e4f08f4..64b3563
Fast-forward
 package.json | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
Restoring local changes.
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
nothing to commit, working directory clean
Dropped stash@{0} (7c28b7f5eaf09dd72ec6e1ea440cbd1611e36c7f)
```

### graft

```
$ git graft development
Your branch is up-to-date with 'origin/master'.
Merge made by the 'recursive' strategy.
 package.json | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
Deleted branch development (was 64b3563).
```

### publish

```
$ git publish
   4.0                        (published)
   changelog                  (published)
   everything-is-not-awesome  (published)
*  master                     (unpublished)
Branch None not found, using current branch master
Publishing master.
Branch master set up to track remote branch master from origin.
```

### unpublish

```
$ git unpublish master
Unpublishing master.
```


## License

[![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png)](http://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, [Steve Mao](https://github.com/stevemao) has waived all copyright and related or neighboring rights to this work.
