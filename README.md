# Ahk-Style-Guide
AutoHotkey style guide, maintained by the community. See [CONTRIBUTING.md](CONTRIBUTING.md) for contributing guidelines.


## Table of Contents

1. [Indentation](#indentation)
1. [Comments](#comments)
1. Hotkeys and Hotstrings
1. [Variables](#variables)
1. Objects and Arrays
1. Flow of Control (If/Else/Loops)
1. Commands
1. Functions
1. Classes
1. Directives


### Indentation

The recommended way to indent is using TABS. 


### Comments

Single-line comments start with a semi-colon (`;`). You should precede the comment text with a space.
```autohotkey
;Wrong
; Right
```

Multi-line comments are enclosed inside `/*` and `*/`
```autohotkey
/* comment
wrong way to comment
*/
/*
comment
right way to comment
*/
```


#### Variables

Prefer using `:=` syntax wherever possible

```autohotkey
var = some string ; Wrong
var := "some string" ; Right
```

Similarly

```autohotkey
var = %onevar%%anothervar% ; Wrong
var := onevar . anothervar ; Right
```