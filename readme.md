# zinit-eza

**Note: zinit and zplugin are different names of the same thing**

An empty repository to aid zplugin's hooks-hacks. You can fork it to have a private copy of it :)

Example uses:

When what's needed is an atclone'' hook to e.g. install a software (plus atpull'' hook to update it):

**dependence：** https://github.com/weineel/zinit-rustup 

```
# The invocation uses https://github.com/zdharma-continuum/null repo as a placeholder
# for the atclone'' and atpull'' hooks
# run-atpull：Even if this repository has not been updated, atpull will still be executed during `zinit update weineel/zinit-eza`.
# atpull"%atclone" :If the same command is used for installation and updating.

# eza: Cargo will build the eza binary and place it in $HOME/.local/share/cargo/bin/eza.
zinit as"program" pick"eza" \
  atclone"cargo install --locked eza" \
  atpull"cargo install --force eza" \
  run-atpull \
  for weineel/zinit-eza

zinit ice from"gh-r" as"completion" pick"completions/zsh/_eza"
zinit light eza-community/eza
```
