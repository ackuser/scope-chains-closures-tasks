TAP version 13
# (anonymous)
ok 1 Solution loaded
ok 2 The structure is correct

1..2
# tests 2
# pass  2

# ok


# Success!

You created a scope chain using lexical scoping and var statements!



-------------------------------------------------------------------------------

# Solution

The scope chain you created now looks like this:

    (global)
        ↑
        |
      foo()
     var bar
        ↑
        |
       zip()
     var quux

By following the arrows, we can see zip() has access to var bar, but not the
other way around.

-------------------------------------------------------------------------------

# Next lesson

Execute scope-chains-closures to move on to the next lesson: Global Scope & Shadowing.
