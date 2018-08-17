# urxvt-matcher-linelimit

Patched default PERL matcher plugin for URxvt.

Adds two configuration variables for the matcher plugin: `lengthLimit` and
`rowLimit`

This will prevent the matcher plugin from checking a line for URLs if the line
is longer than the value defined in `lengthLimit` or if it is higher than
`rowLimit` in buffer.

## Example     
![Example of line too long to trigger matcher and a regular matched line][img]

## Why?

The matcher plugin can cause slowdowns when the buffer is getting huge. I want
URxvt to be the fastest possible, so I wanted to give a possibility to limit
the effects without having to entirely disable the matcher plugin.

## Installation

Copy `matcher` to one of your URxvt PERL lib directories. ie:
`~/.urxvt/ext/`.

## Configuration

Without any configuration, the default matcher plugin behavior is kept. To add
restrictions on line length/row, add the following lines to your **X
resources**:
```
URxvt.matcher.lengthLimit: 240
URxvt.matcher.rowLimit: 100
```
You can use any other value, but I recommend 240 and 100.

0 = no limit.

Example variables block in `~/.Xresources` with matcher plugin configuration:
```
 URxvt.perl-ext-common: default,matcher,tabbedex,resize-font
 
 URxvt.url-launcher: /usr/bin/xdg-open
 URxvt.matcher.button: 1
 URxvt.matcher.rend.0: Uline fg4
 URxvt.matcher.rowLimit: 100
 URxvt.matcher.lengthLimit: 240
 ```

## Thanks

Inspired by [this section][wiki section] in the URxvt article on
[ArchWiki][archwiki].

## Self promotion

Check out my [Dotfiles][dotfiles] if you want to see other URxvt and UNIX tips
I did and/or use.

[img]: .gh/example.png
[archwiki]: https://wiki.archlinux.org/index.php/ArchWiki:About
[wiki section]: https://wiki.archlinux.org/index.php/Rxvt-unicode#Very_long_lines_cause_slowdown
[dotfiles]: https://github.com/skielred/Dotfiles
