# Sample codes

## Hello, World

```
import std.io

def main():
  std.io.putStrLn "Hello, world!"
```

## variables

```
def main():
  var x = 1   // creates mutable variable x
  x += 1      // OK, x can be modified
  x = x * 2   // x can be re-assigned

  val y = 1       // creates immutable value y
  // y = y * 2    // NG, cannot be re-assigned nor modified
  // val y = 2    // NG, value y is already defined
  val! y = y * 2  // OK, shadows old value (not modified)

  def z = 1       // z is compile-time constant 1
  // z = 2        // NG
  // def  z = 2   // NG, z is already defined
  // def! z = 2   // NG, constants cannot be shadowed in same scope
  def f():
    def z = 3   // OK
    pass        // (cannot close code-block with declaration)

  return
```

## functions

```
// without parameters

def f() -> int:   // return type is given, f :: () -> int
  return 1

def g():    // return type is not given
  return 1  // g :: () -> int, infered from return statement

def h():
  pass    // h :: () -> unit, because no return statement is there

// with parameters

def f1(x :: int) -> int:  // f1 :: (int) -> int
  pass      // compile error, because f1 returns non-unit-like type
            // but f1 has no return statement

def g1(x :: int):
  return x        // g1 :: (int) -> int, infered from return statement

def f2(x :: int, y :: int) -> int:
  return x + y    // f2 :: (int, int) -> int

// recursion
def factorial(x :: int):
  if x <= 1:
    return 1
  else:
    return x * factorial(x - 1)
```
