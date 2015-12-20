TAP version 13
# (anonymous)
ok 1 Solution loaded
not ok 2 The structure is correct
  ---
    operator: equal
    expected:
      '(global)\n\tfoo()\n\t- var bar\n\t- quux = ?\n\treturn zip\n\t\tzip()\n\t\t- var quux\n\t\t- bar = ?'
    actual:
      '(global)\n\tfoo()\n\t- var bar\n\t- quux = ?\n\t\tzip()\n\t\t- var quux\n\t\t- bar = ?'
  ...

1..2
# tests 2
# pass  1
# fail  1


# Almost there!

Check the errors above to see where you went wrong.

# Hints

  * The task is to return the function `zip`, not the result of `zip()`.
  * The value you set to `bar` isn't important.

# More Help

  * If you're still having troubles, post a question in the nodeschool issues repository: http://bit.ly/scope-chains-question


  TAP version 13
  # (anonymous)
  ok 1 Solution loaded
  ok 2 The structure is correct

  1..2
  # tests 2
  # pass  2

  # ok


  # Success!

  Awesome stuff - you closed over the variable bar inside zip, then returned
  zip.



  -------------------------------------------------------------------------------

  # Solution

  Let's look at the scope chain for your solution:

        foo()
       var bar
      return zip
          ↑
          |
        zip()
      bar = true

  By referencing bar within zip, we have created a Closure where zip() closes over the variable bar from its parent scope foo().

  Since we are returning the function zip, the reference to bar is maintained (and hence the closure is maintained) until zip is no longer required.

  This has interesting implications for memory, which we will cover in the next lesson.

  -------------------------------------------------------------------------------

  # Next lesson

  Execute scope-chains-closures to move on to the next lesson: Garbage Collection.
