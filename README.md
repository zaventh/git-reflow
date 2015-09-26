git-reflow
========

A collection of Git extensions to provide high-level repository operations. Heavily based on Vincent Driessen's [branching model](http://nvie.com/git-model "original blog post"), but modified to prefer rebasing over non-ff merging.


Installing git-reflow
-------------------
* Uninstall git-flow.
* Clone git-reflow repository
* execute `sudo make install`


Integration with your shell
---------------------------
For those who use the [Bash](http://www.gnu.org/software/bash/) or [ZSH](http://www.zsh.org) shell, please check out the excellent work on the [git-flow-completion](http://github.com/bobthecow/git-flow-completion) project by [bobthecow](http://github.com/bobthecow). It offers tab-completion for all git-flow subcommands and branch names.


License terms
-------------
git-flow is published under the liberal terms of the BSD License, see the [LICENSE](LICENSE) file. Although the BSD License does not require you to share any modifications you make to the source code, you are very much encouraged and invited to contribute back your modifications to the community, preferably
in a Github fork, of course.


### Initialization

To initialize a new repo with the basic branch structure, use:
  
		git flow init [-d]
  
This will then interactively prompt you with some questions on which branches you would like to use as development and production branches, and how you would like your prefixes be named. You may simply press Return on any of those questions to accept the (sane) default suggestions.

The ``-d`` flag will accept all defaults.


### Creating feature/release/hotfix/support branches

* To list/start/finish feature branches, use:
  
  		git flow feature
  		git flow feature start <name> [<base>]
  		git flow feature finish <name>
  
  For feature branches, the `<base>` arg must be a commit on `develop`.

* To push/pull a feature branch to the remote repository, use:

  		git flow feature publish <name>
		  git flow feature pull <remote> <name>

* To list/start/finish release branches, use:
  
  		git flow release
  		git flow release start <release> [<base>]
  		git flow release finish <release>
  
  For release branches, the `<base>` arg must be a commit on `develop`.
  
* To list/start/finish hotfix branches, use:
  
  		git flow hotfix
  		git flow hotfix start <release> [<base>]
  		git flow hotfix finish <release>
  
  For hotfix branches, the `<base>` arg must be a commit on `master`.

* To list/start support branches, use:
  
  		git flow support
  		git flow support start <release> <base>
  
  For support branches, the `<base>` arg must be a commit on `master`.
