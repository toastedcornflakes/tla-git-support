# TLA+ git support

Git filter to commit TLA+ files without including the pluscal translation.

The filter is automatically called when staging file with git, using [`git-attributes`](https://git-scm.com/book/en/v2/Customizing-Git-Git-Attributes).

The files in the working directory are not modified. The file added to the staging area will not contain the pluscal translation (delimited by BEGIN TRANSLATION and END TRANSLATION comments).

## Installation

```sh
$ cd your_repository
$ cat tla-git-support/.gitattributes >> .gitattributes
$ cp tla-git-support/pluscal_clean.sh .

$ git config --local filter.pluscal.clean ./pluscal_clean.sh
$ git config --local filter.pluscal.smudge cat
```
