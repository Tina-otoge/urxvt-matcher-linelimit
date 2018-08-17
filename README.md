# urxvt-matcher-linelimit

Patched default PERL matcher plugin for URxvt.

Adds two configuration variables for the matcher plugin: `lengthLimit` and
`rowLimit`

This will prevent the matcher plugin from checking a line for URLs if the line
is longer than the value defined in `lengthLimit` or if it is too higher than
`rowLimit` in buffer.

## Example     
![Example of line too long to trigger matcher and a regular matched line](
.gh/example.png)

## Installation

Copy `matcher` to one of your URxvt PERL lib directories. ie:
`~/.urxvt/ext/`.

## Configuration

Without any configuration, the default matcher plugin behavior is kept. To add
restrictions one line length/row, add the following lines to your **X
resources**:
```
URxvt.matcher.lengthLimit: 240
URxvt.matcher.rowLimit: 100
```
You can use any other value, but I recommend 240 and 100.

0 = no limit.

## Self promotion

Check out my [Dotfiles](https://github.com/skielred/Dotfiles) if you want to
see other URxvt and UNIX tips I did/use.
