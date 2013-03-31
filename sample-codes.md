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
  var x = 1   # creates mutable variable x
  x += 1      # OK, x can be modified
  x = x * 2   # x can be re-assigned

  val y = 1       # creates immutable value y
  # y = y * 2     # NG, cannot be re-assigned nor modified
  # val y = 2     # NG, value y is already defined
  val! y = y * 2  # OK, shadows old value (not modified)

  def z = 1     # z is compile-time constant 1
  # z = 2       # NG
  # def  z = 2  # NG, z is already defined
  # def! z = 2  # NG, constants cannot be shadowed in same scope
  def f():
    def z = 3   # OK
    pass        # (cannot close code-block with declaration)

  return
```
