# break challenges

This guide will show you how to use a break statement within a while loop. #docs

### Challenge 0

Welcome! This [guided tutorial](/lessons/break/tutorial) will assist you with this activity.

```
count = 0
shouldBreak = false
input.onButtonPressed(Button.A, () => {
    shouldBreak = true
})
while (true) {
    if (shouldBreak) {
        basic.showString("I'M OUT!", 150)
        images.createImage(`
# . . . #
# . . . #
. . # . .
# . . . #
. # # # .
`).showImage(0)
        break
    }
    count = count + 1
    basic.showNumber(count, 150)
    basic.pause(1000)
}
```

### Challenge 1

Try to remove the `break` in the `if` loop. What problem does this create?

### Challenge 2

Now let's resume the timer again once button `B` is pressed! To do so, begin by creating a condition to know when button `B` is pressed.

```
// **. . .**
while (true) {
    if (shouldBreak) {
        basic.showString("I'M OUT!", 150)
        break
    }
    count = count + 1
    basic.showNumber(count, 150)
    basic.pause(1000)
}
input.onButtonPressed(Button.B, () => {
}) // ***
```

Next, set `shouldBreak` back to false to indicate we want to run the `while` loop again.

```
// **. . .**
input.onButtonPressed(Button.B, () => {
    shouldBreak = false // ***
})
```

And now copy the code from the previous while loop into the condition of `input->on button pressed("B")`. This will resume the counter.

```
// **. . .**
input.onButtonPressed(Button.B, () => {
    shouldBreak = false
    while (true) {
        if (shouldBreak) {
            basic.showString("I'M OUT!", 150) // ***
            break // ***
        }
        count = count + 1 // ***
        basic.showNumber(count, 150) // ***
        basic.pause(1000) // ***
    }
})
```

### Challenge 3

Notice that the two `while` loops are identical. Clean up this redundancy in your code by creating another method and then placing the `while` loop in the method.

