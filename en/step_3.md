## Reading a Clue

In this step, you will create an input field which takes user inputs and adjusts them to fit the structures needed to use `DictionaryLookup`.

We want to be able to input the clue in plain text, so that we can look up whatever we want, without having to use all those `~~`.

In order to do this, we need to have an `InputField`, so that the user can input their crossword clue.

```InputField[x]```

An `InputField` isn't very useful unless we can read what the user typed, and use it for computation. In order to use what is typed into the box, we can make use of the `Dynamic` function. `Dynamic` allows us to update values depending on the input.

```
{InputField[Dynamic[x]], Dynamic[x]}
```

When you run this code, type into the `InputField`, and press Return, you'll see that the `Dynamic` value updates. This means that we can use `Dynamic[x]` in other places in the code, and the value will update whenever we change what's inside the `InputField`.

We can customise the `InputField` a little more, in order to make it easier to use the input later on.

--- task ---

Create an `InputField` with a `Dynamic` variable which updates whenever the input is changed.

Customise the `InputField` so that it interprets every input as a `String`.

```{InputField[Dynamic[x], String, ContinuousAction -> True], Dynamic[x]}```

--- /task ---