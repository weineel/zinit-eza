# zinit-zellij

**Note: zinit and zplugin are different names of the same thing**

An empty repository to aid zplugin's hooks-hacks. You can fork it to have a private copy of it :)

Example uses:

When what's needed is an atclone'' hook to e.g. install a software (plus atpull'' hook to update it):

**dependence：** https://github.com/weineel/zinit-rustup 

```
# The invocation uses https://github.com/zdharma-continuum/null repo as a placeholder
# for the atclone'' and atpull'' hooks
# run-atpull：Even if this repository has not been updated, atpull will still be executed during `zinit update weineel/zinit-zellij`.
# atpull"%atclone" :If the same command is used for installation and updating.

zinit as"program" pick"zellij" \
  atclone"cargo install --locked zellij && zellij setup --generate-completion zsh > ./_zellij" \
  atpull"cargo install --force zellij && zellij setup --generate-completion zsh > ./_zellij" \
  run-atpull \
  for weineel/zinit-zellij
```
