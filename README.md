# irodolist

Irodolist manages LSCOLORS/LS_COLORS and zsh completion colors.  
This project is an example project of [kmhjs/zcl](https://github.com/kmhjs/zcl) .

## Usage

1. Clone this project. (Or download `irodolist` and example `config` file)
2. Clone [kmhjs/zcl](https://github.com/kmhjs/zcl) project. (Or download `zcl` file)
3. Update your `FPATH` with path to `irodolist` and `zcl` file.
4. Call `autoload -Uz zcl` and `autoload -Uz irodolist` in `.zshrc` etc.
5. Configure your `ls-colors.conf` .
6. Run irodolist as `irodolist ls-colors.conf` .

### Example result

Following example result is for attached `ls-colors.conf` .

```
$ irodolist ls-colors.conf
LSCOLORS       : ExFxCxDxBxegedabagacad
LS_COLORS      : di=01;34;:ln=01;35;:so=01;32;:pi=01;33;:ex=01;31;:bd=00;34;46;:cd=00;34;43;:su=00;30;41;:sg=00;30;46;:tw=00;30;42;:ow=00;30;43;
zsh completion : 'di=01;34;' 'ln=01;35;' 'so=01;32;' 'pi=01;33;' 'ex=01;31;' 'bd=00;34;46;' 'cd=00;34;43;' 'su=00;30;41;' 'sg=00;30;46;' 'tw=00;30;42;' 'ow=00;30;43;'
```

## Configuration format

### Format

Predefined format is here.

```
(
  :target     ${target}
  :foreground ${color}
  :background ${color}
  :attribute  ${text_attribute}
)
```

For making configuration with this format, following predefined values can be used.

__`${target}`__

* `directory`
* `symbolic_link`
* `socket`
* `pipe`
* `executable`
* `block_device`
* `character_device`
* `executable_setuid`
* `executable_setgid`
* `writable_directory_stickybit`
* `writable_directory`

__`${color}`__

* `black`
* `red`
* `green`
* `yellow`
* `blue`
* `magenta`
* `cyan`
* `white`

__`${text_attribute}`__

* `normal`
* `bold`

### Example

```
(
  :target     directory
  :foreground blue
  :background default
  :attribute  bold
)
(
  :target     symbolic_link
  :foreground magenta
  :background default
  :attribute  bold
)
(
  :target     socket
  :foreground green
  :background default
  :attribute  bold
)
```

## License

This project is distributed under MIT License. See `LICENSE` .

## Misc

Currently, this project is under development.
