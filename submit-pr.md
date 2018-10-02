# Submit a PR

## Setup remotes

### From scratch

1. Go on the github page of the repo you want to contribute to
2. _Fork the repo to your account
3. From the page of your fork, get the clone link
   (prefer ssh authentification to https)
  

```
git clone <fork-repo-link>
git remote add upstream <original-upstream-repository-link>
```

For example, with mis builder:

```
git clone git@github.com:robinkeunen/mis-builder.git
git remote add upstream git@github.com:OCA/mis-builder.git
```

If your setup is correct, `git remote -v` should return something like:

```
git remote -v    
> origin	git@github.com:robinkeunen/mis-builder.git (fetch)
> origin	git@github.com:robinkeunen/mis-builder.git (push)
> upstream	git@github.com:OCA/mis-builder (fetch)
> upstream	git@github.com:OCA/mis-builder (push)
``` 

### Reset upstream and origin

When typing `git remote -v`, if you get something like:

```git
git remote -v
> origin	https://github.com/OCA/sale-workflow.git (fetch)
> origin	https://github.com/OCA/sale-workflow.git (push)
```

Use these commands

```
git remote add upstream <original-upstream-repository-link>
git remote remove origin
git remote add origin <forked-repository-link>
```
