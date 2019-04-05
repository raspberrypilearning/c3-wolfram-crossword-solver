## Read a clue

In this step, you will create an input field which takes user inputs and adjusts them to fit the structures needed to use `DictionaryLookup`.

You want to input the clue in plain text, so that you can look up whatever you want without having to use tilde signs `~~`.

In order to do this, you need to create an `InputField` where the user can input their crossword clue.

```
InputField[x]
```

An `InputField` isn't very useful unless the program can read what the user typed in. To allow the program to read the input, you can use the `Dynamic` function. `Dynamic` updates values depending on the input.

```
{InputField[Dynamic[x]], Dynamic[x]}
```

Run this code, type into the `InputField`, and press <kbd>Enter</kbd>.

You should see that the `Dynamic` value updates. This means that you can use `Dynamic[x]` in other places in the code, and the value will update every time the `InputField` input changes.

Now, customise the `InputField` a little more, in order to make it easier to use the input later on.

--- task ---

Create an `InputField` with a `Dynamic` variable that updates whenever the input is changed.

Customise the `InputField` so that it interprets every input as a `String`.

```{InputField[Dynamic[x], String, ContinuousAction -> True], Dynamic[x]}```

--- /task ---
