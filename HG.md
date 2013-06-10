# Mercurial

Gecko and Firefox are in Mercurial. You will use hg to manage this source.

## Setup Configs

Use an `.hgrc` file, much like [jedp](https://gist.github.com/jedp/3778932).

```
[ui]
#merge = kdiff3
username = Austin King <aking@mozilla.com>

[diff]
# git diff is required so binary files don't break
git = 1
showfunc = True
unified = 8

[defaults]
diff=-p -U 8
commit= -v

[paths]
# makes it easier to push to try
try = ssh://hg.mozilla.org/try

[extensions]
# I don't even remember what these are all for
graphlog =
hgext.mq =
fetch =
purge =
hgext.rebase =
hgext.extdiff =
hgext.transplant =
# rdiff=/home/jed/lib/python/rdiff.py
# this lets you import patches straight from bugzilla
# source: https://hg.mozilla.org/users/robarnold_cmu.edu/qimportbz
# about:    http://robarnold.org/2009/06/02/hg-qimport-my-bugzilla-patch-redux.html
# qimportbz=/path/to/your/qimportbz/

[extdiff]
# Creates the command 'hg cdiff' for colorized diff output
cmd.cdiff = colordiff
opts.cdiff = -wuprN

[merge-tools]
# Specify command line
# kdiff3.args = $base $local $other -o $output
# Give higher priority
# kdiff3.priority = 1

[bookmarks]
track.current = True
```

## Patch Queues

Learn to use [Mercurial Queues](https://developer.mozilla.org/en-US/docs/Mercurial_Queues).