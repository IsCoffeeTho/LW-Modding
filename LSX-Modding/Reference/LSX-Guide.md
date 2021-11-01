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
### Prerequisites
When refering to the states of pegs it is recommended to use:
`HIGH` for 1, On, Red, Active.
`LOW` for 0, Off, Black, Inactive.

### `out`
The `out` keyword allows you to set the output pins either `HIGH` or `LOW`.

### `mem`
The `mem` keyword is a way to store persistent data between ticks of execution.
`mem` has a capacity of 256 Bits. The capacity is a factor to be careful about.

Here is a simple script that:
* Saves a bit on `CLK` `HIGH`.
* Outputs the Bit on `CLK` `LOW`.
```lsx
if in[0]
  mem[0] = in[1]
end

if !in[0]
  out[0] = mem[0]
end
```
