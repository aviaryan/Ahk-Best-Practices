# Ahk-Style-Guide
AutoHotkey style guide, maintained by the community. See [CONTRIBUTING.md](CONTRIBUTING.md) for contributing guidelines.


## Table of Contents

1. [Indentation](#indentation)
1. [Comments](#comments)
1. Hotkeys and Hotstrings
1. [Variables](#variables)
1. [Arrays and Objects](#arrays-and-objects)
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


### Variables

Prefer using `:=` syntax wherever possible

```autohotkey
var = some string ; Wrong
var := "some string" ; Right
var = %onevar%%anothervar% ; Wrong
var := onevar . anothervar ; Right
```

Use concatenate (`.`) operator to break a long string into several lines rather than writing it in one line.

```autohotkey
; wrong
var := "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolore eos quas, sapiente sed voluptate repellendus asperiores modi excepturi ea ullam."
; right
var := "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officia laboriosam inventore"
    . "laudantium voluptas voluptate quasi, quae dolor unde repellendus quo."
```


### Arrays and Objects

Use one space between values or key-value pairs in an Array declaration.
```autohotkey
Array := [2,4,6,8] ;wrong
Array := [2, 4, 6, 8] ;right
AssociativeArray := {key1: Value1,key2:Value2, key3:Value3} ; wrong
AssociativeArray := {key1: Value1, key2: Value2, key3: Value3} ; right
```