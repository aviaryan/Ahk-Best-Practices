# AutoHotkey Best Practices
Good practices in AutoHotkey coding that will help avoid bugs and make your code more readable. This is currently a work in progress. Additions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for contributing guidelines.


## Table of Contents

1. [Indentation](#indentation)
1. [Comments](#comments)
1. [Hotkeys and Hotstrings](#hotkeys-and-hotstrings)
1. [Variables](#variables)
1. [Strings](#strings)
1. [Arrays and Objects](#arrays-and-objects)
1. [Flow of Control](#flow-of-control)
    1. [If/Else](#ifelse)
    1. Loops
    1. More
1. [Commands](#commands)
1. Functions
1. Classes
1. Directives
1. [Naming Convention](#naming-convention)


### Indentation

* Indentation makes your code more readable and easy to debug and understand. You may use TABS or a consistent amount of spaces for indentation. ([Source](https://autohotkey.com/docs/Tutorial.htm#s84))
```autohotkey
if (car == "old")
{
   msgbox, the car is really old
   if (wheels == "flat")
   {
      msgbox, this car is not safe to drive.
      Return
   }
   else
   {
      msgbox, Be careful! This old car will be dangerous to drive.
   }
}
else
{
   msgbox, My`, what a shiny new vehicle you have there.
}
```


### Comments

* Single-line comments start with a semi-colon (`;`). You should precede the comment text with a space.
```autohotkey
;Bad
; Good
```

* Multi-line comments are enclosed inside `/*` and `*/`
```autohotkey
/* comment
bad way to comment
*/
/*
comment
good way to comment
*/
```


### Hotkeys and Hotstrings

* For hotkeys, it is recommended to use multi-line syntax with `return`. `Return` will end the execution of the current executing subroutine. So in the following example, the 
execution after pressing Ctrl+J ends when `Return` is encountered. ([Source](https://autohotkey.com/docs/Tutorial.htm#Text_instructions_6))
```autohotkey
^j::
    Send, My First Script
Return
```


### Variables

* Prefer using `:=` syntax wherever possible. It avoids confusion between variable names and literal strings.
```autohotkey
var = some string ; bad
var := "some string" ; good
var = %onevar%%anothervar% ; bad
var := onevar . anothervar ; good
var = 2 ; bad
var := 2 ; good
```

* Try to use the variable in the same case at different places.


### Strings

* Use concatenate (`.`) operator to break a long string into several lines rather than writing it in one long line.
```autohotkey
; bad
var := "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dolore eos quas, sapiente sed voluptate repellendus asperiores modi excepturi ea ullam."
; good
var := "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officia laboriosam inventore"
    . "laudantium voluptas voluptate quasi, quae dolor unde repellendus quo."
```

* For multi-line strings, prefer `(...)` syntax over manually adding \`n at the end of every line.
```autohotkey
; bad
s := "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Totam, minima!`n"
    . "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eum, eaque.`n"
    . "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Et, veniam."
; good
s := "
(
Lorem ipsum dolor sit amet, consectetur adipisicing elit. Totam, minima!
Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eum, eaque.
Lorem ipsum dolor sit amet, consectetur adipisicing elit. Et, veniam.
)"
```
You can even use variables in between. 
```autohotkey
s := "
(
Line number 1
Line number 2
)" . myVar . "
(
Line number 5
Line number 6
)"
```


### Arrays and Objects

* Use one space between values or key-value pairs in an Array declaration. It looks nicer.
```autohotkey
Array := [2,4,6,8] ;bad
Array := [2, 4, 6, 8] ;good
AssociativeArray := {key1: Value1,key2:Value2, key3:Value3} ; bad
AssociativeArray := {key1: Value1, key2: Value2, key3: Value3} ; good
```


### Flow of Control

#### If/Else

* In IF statements, use `==` instead of `=` for comparing. Again this avoids confusion and lots of bugs.
```autohotkey
var := "AHK"

; bad
if var = AHK
    msgbox match

; good
if (var == "AHK")
    msgbox match
```


### Commands

* It is OK to omit the comma (,) if only one argument of a command is specified.
```autohotkey
WinClose Notepad
```

* Try to not use `%var%` variable syntax. It will be deprecated in AHK v2 and also is not consistent with many other programming languages around.
```autohotkey
; bad
Run Notepad.exe %myFile%
; good
Run % "Notepad.exe " myFile
```


### Naming Convention

* Variable names consisting of many words should use camelCase or underscores for distinction. 
```autohotkey
farthestplanet := "Pluto" ; bad
farthest_planet := "Pluto" ; good
farthestPlanet := "Pluto" ; good
```

* Variable names should be logical and should convey meaning about their purpose.  
```autohotkey
i := 40 ;bad
x_margin := 40 ;good
ff := "test.pdf" ;bad
fileName := "test.pdf" ;good
```

* Class names should use PascalCase. This is consistent with many programming languages like C++, Python and Java.
```autohotkey
; bad
class myclass {
    
}
; good
class MyClass {
    
}
```


## Thanks

* Awesome people for their suggestions in the [AutoHotkey forum topic](https://autohotkey.com/boards/viewtopic.php?f=17&t=14089)
