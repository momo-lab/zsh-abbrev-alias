# zsh-abbrev-alias
This zsh plugin provides functionality similar to Vim's abbreviation expansion.

This plugin consulted http://zshwiki.org/home/examples/zleiab .

## Installation
### Using [zplug](https://github.com/b4b4r07/zplug)

```zsh
zplug "momo-lab/zsh-abbrev-alias"
```

Alias settings are written after `zplug load`.

## For Example

```zsh
$ abbrev-alias -g G="| grep"
$ ps aux G<push space key>
->
$ ps aux | grep 
```

```zsh
$ git branch
* master
$ abbrev-alias -g -e B='$(git symbolic-ref --short HEAD 2> /dev/null)'"
$ git push origin B<push space key>
->
$ git push origin master 
```

## Help
Show `abbrev-alias --help`.

```zsh
$ abbrev-alias --help
abbrev-alias 0.2.0
usage: abbrev-alias [OPTIONS] {name=value ...}
       abbrev-alias -u {name ...}
       abbrev-alias --init

options:
  -c, --command   register as 'alias name=value'
  -g, --global    register as 'alias -g name=value'
  -e, --eval      evaluates subshells on expansion.
  -i, --init      initialize abbrev-alias. execute with .zshrc
  -h, --help      show this help
  -v, --version   show version
```
