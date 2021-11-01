# Logic Script - Reference
## Contents
* [Control Statements](#control-statements)
* [Keywords](#keywords)

## Control Statements
### `if <expression>`
The `if` statement will run once if the expression is true.

```lsx
if <expression>
  ...
end
```
```c
// Equivelant C code
if (<expression>) {
  ...
}
```
### `while <expression>`
The `while` statment runs once every tick if the expression is true.

```lsx
while <expression>
  ...
end
```
```c
// Equivelant C code
while (<expression>) {
  ...
}
```
### `once`
The `once` statement runs once every tick every time.

```lsx
once
  ...
end
```
```c
// Equivelant C code
while (true) {
  ...
}
```
### `any`
The `any` statement runs on any logical change.

```lsx
any
  ...
end
```
```c
// Equivelant C code
if (currentIn != previousIn) {
  ...
  previousIn = currentIn;
}
```
## Keywords
