# Git @ Coop IT Easy

> Idéalement, il faudrait travailler avec un repo principal Coop IT Easy et des fork personnels.
> Mais on va commencer par travailler Rémy et moi depuis nos fork et Houssine directement depuis son repo.


## Flow

> Branch early, branch often.

### Working from origin

**Starting a new development/feature/bugfix**


```
 git checkout master
 git checkout -b my-bugfix
 # do your work
 git add my_files.py
 git commit  # cf "a good commit message"
 git push 
```

Log into github on the repository page, a pop up should appear with the last push you made.
Click on `create pull-request` and off you go.


### Working from a fork

**Set up upstream repository**

```
# fork from main repository
git remote add upstream https://github.com/houssine78/vertical-cooperative
git config --global push.default current
```

**Starting a new development/feature/bugfix**

```
 cfrp  # cf aliases, synchronise upstream / origin / local
 git checkout -b my-bugfix
 # do your work
 git add my_files.py
 git commit  # cf "a good commit message"
 git push 
```

If you have `hub` installed, submit pull-requests to upstream using `git pull-request`. 
Otherwise, log into the upstream repository, a pop up should appear with the last push you made.
Click on `create pull-request` and off you go.

> Before merging, rebase your work on 9.0 to end up with a cleaner branching tree.

### Useful commands for clean committing

**Add some code to the last commit**

```
git add somefile.py
git commit  --amend
git push force
```

**Add some code to an old commit**

```
 git add somefile.py
 git commit --fixup 3e89326 # fixed commit
 git push
 # when ready to merge in 9.0
 git rebase -i --autosquash upstream/master
 git push force
```

**Work on someone else's branch**

```
 git remote add robinkeunen git@github.com:robinkeunen/addons
 git remote -v (view list)
 git fetch robinkeunen
 git checkout robinkeunen/some_branch
```

## Commit Message Guidelines

`tl;dr`: Short summary (72 chars) on the first line. 
Detailed explanation below.

```
Short (72 chars or less) summary

More detailed explanatory text. Wrap it to 72 characters. The blank
line separating the summary from the body is critical (unless you omit
the body entirely).

Write your commit message in the imperative: "Fix bug" and not "Fixed
bug" or "Fixes bug." This convention matches up with commit messages
generated by commands like git merge and git revert.

Further paragraphs come after blank lines.

- Bullet points are okay, too.
- Typically a hyphen or asterisk is used for the bullet, followed by a
  single space. Use a hanging indent.
```

[reference](https://gist.github.com/robertpainsi/b632364184e70900af4ab688decf6f53)

## Aliases:

setup: use [OhMyZsh!](http://ohmyz.sh/) or put these aliases in home/.aliases file (ex: `alias gpf='git push -f'`)

- `cfrp`: git checkout 9.0 && git fetch upstream && git rebase upstream/9.0 && git push origin 9.0
- `gcb` :  git checkout -b
- `gca -m "msg"` : commit all modif with message "msg"
- `gc!` : git commit --amend
- `gca!`: git commit -a --amend
- `gpf` : git push -f
- `gru`: git rebase -i --autosquash upstream/master

[cheatsheet](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)

## Notes on migrating to coop it easy's github

1. Isoler les différents _packages_ de coop it easy (par exemple: isoler les différents packages relatifs à EasyMyCoop),
2. Créer le repo coopiteasy/easymycoop
3. Dupliquer l'entièreté de houssine/addons dans le nouveau repo
4. retirer les modules qui n'ont rien à voir avec EasyMyCoop

References:

- [Moving git repository and all its branches, tags to a new remote repository keeping commits history](https://gist.github.com/niksumeiko/8972566)
- [Duplicating a repository](https://help.github.com/articles/duplicating-a-repository/)