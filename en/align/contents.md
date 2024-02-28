# Align text

Create a file called `align.py` and implement a function `right_align(text)` which right aligns the given text.

    text = "ASDF is the sequence of letters that appear\non the first four keys on the home row of\na QWERTY or QWERTZ keyboard. They are often used\nas a sample or test case or as random, meaningless\nnonsense. It is also a common learning tool\nfor keyboard classes, since all four keys are\nlocated on Home row." # from the wikipedia
    print(text)
    print()
    print(right_align(text))

Expected ouput:

    ASDF is the sequence of letters that appear
    on the first four keys on the home row of
    a QWERTY or QWERTZ keyboard. They are often used
    as a sample or test case or as random, meaningless
    nonsense. It is also a common learning tool
    for keyboard classes, since all four keys are
    located on Home row.

           ASDF is the sequence of letters that appear
             on the first four keys on the home row of
      a QWERTY or QWERTZ keyboard. They are often used
    as a sample or test case or as random, meaningless
           nonsense. It is also a common learning tool
         for keyboard classes, since all four keys are
                                  located on Home row.



## Specification

* The programm should contain the function `right_align(text)`.
* The input of the function is a `string` called `text`.
* The output of the function is a string where each line is padded with spaces so that all lines are right aligned.  
* The alignment should be done in such a way that the text doesn't move more to the right than strictly necessary.

### Constraints

* You are only allowed to use the concepts that are discussed in this module. Except for the mentioned exceptions.
For an overview of those concepts have a look [here](/python/en/overview).
* You are *not* allowed to use the `import`-statement.
* You can use other string methods (like `split()`), mentioned in the python [string functions documentation](https://docs.python.org/3.7/library/stdtypes.html#string-methods).
* You can use the built-in python function `len()`.
* The function `right_align(text)` should not contain any print statements.
* You **are alowed** to use string multiplication.

## Background

You already know how to use `.split()` to split a string into a list of strings based on a specific character.

In strings, newlines can be inserted by writing `\n`. So you might do this[^1]:

    text = "Beautiful python\nExplicit and simple form\nWinding through the clouds"
    print(text)

Output:

    Beautiful python
    Explicit and simple form
    Winding through the clouds

You may also add a newline to an existing string:

    text = "Yes, "
    text += "we"
    text += "\n"
    text += "can!"

Output:

    Yes, we
    can!

## Strategy


1. Split up the text into individual **lines** (based on the newline character, `\n`).

2. Find the length of longest line.

3. Create a variable to hold the newly made string.

4. For every line:

    - Add padding spaces to the left to make it the same length as the longest line.

    - Add the padded line to output text.

## Testing

Try some of the following testcases:

### Test 1

    text = "This text is left aligned.\nLets change that."
    print(text)
    print()
    text_right_aligned = right_align(text)
    print(text_right_aligned)

#### Expected output:

    This text is left aligned.
    Lets change that.

    This text is left aligned.
             Lets change that.

### Test 2

    text = "It would be so\nnice if something made\nsense for a change."
    print(text)
    print()
    text_right_aligned = right_align(text)
    print(text_right_aligned)

#### Expected output:

    It would be so
    nice if something made
    sense for a change.

            It would be so
    nice if something made
       sense for a change.

#### Test 3

    text = "# #\n# # #\n# # # #"
    print(text)
    print()
    text_right_aligned = right_align(text)
    print(text_right_aligned)

#### Expected output:

    # #
    # # #
    # # # #

        # #
      # # #
    # # # #

#### Test 4

    bunny = right_align("(\\ (\\ \nbunny! =>     ( ^.^)\n*(\")(\")")
    print(bunny)

#### Expected output:

                  (\ (\
    bunny! =>     ( ^.^)
                 *(")(")

### Checkpy

checkpy align
