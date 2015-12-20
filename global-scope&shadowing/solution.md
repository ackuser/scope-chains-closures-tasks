
TAP version 13
# (anonymous)
ok 1 Solution loaded
ok 2 The structure is correct

1..2
# tests 2
# pass  2

# ok


# Success!

You assigned a value to quux, even though foo() doesn't have access to the
quux inside zip().



-------------------------------------------------------------------------------

# Solution

The scope chain of the solution looks like this:

    (global)
      quux
        ↑
        |
      foo()
     var bar
        ↑
        |
       zip()
     var quux

Following the arrows, we can see that the quux assigned inside foo() has
become globally scoped. This is a different quux from the one inside zip(),
which now shadows the globally scoped quux.

-------------------------------------------------------------------------------

# Next lesson

Execute scope-chains-closures to move on to the next lesson: Closures.
