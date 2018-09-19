# Odoo Onboarding @ Coop IT Easy

## odoo

- Installation
- Odoo is modular
- Odoo classic cli options
  - -c -u -i -d --db-filter --stop-after-init
- MVC:
  - Models: creating and inheriting modules
  - Views: xml and qweb views
- Debug mode

## git

- Basics:
  - index, stage, commit
  - git add, commit, branch, merge, rebase
  - git push, pull
- Strategies
  - local
  - central remote: local + origin
  - distributed remotes: local + origin + upstream
- Clean pull requests
  - cfrp and rebase feature branch
  - git commit --amend
  - git commit --fixup, git rebase -i --autosquash

```
# cfrp
git checkout 9.0
git fetch upstream 9.0
git rebase upstream/9.0 9.0
git push origin 9.0
``` 

## ressources:

- Odoo Essentials
- Odoo basic configuration file
- [Learn git branching](https://learngitbranching.js.org/)