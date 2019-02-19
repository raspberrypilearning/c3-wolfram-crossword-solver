## Building an Interface

Now that you've written code which takes the user input from an `InputField` and uses Wolfram Alpha to look up the pattern in the dictionary, returning a list of possible words, you can start to build an interface.

--- task ---
Let's use `Column` and `Framed` to put the possible words into a box.

You can alter your code from the previous task.

```
x = "c_t";
InputField[Dynamic[x], String, ContinuousAction -> True]
Dynamic[
Framed[Column[ReleaseHold[WolframAlpha[x, "WolframParse"]]]]]
```
---/task ---

You may have noticed that your `InputField` and your results are two separate outputs. We can fix this by putting both pieces of code inside a `Column`. At the same time, we can add a title, and instructions on how to use the tool.

--- task ---
+ Use what you learned about `Column` and `Framed` in the last task to put both of your outputs into a single, framed column.
+ Add text to explain the instructions, and to lable the `InputField` and the list of words.
+ Use `Text` and `Style` to customise the look of the text.
+ You can alter your code from the previous task.

```
Framed[Column[{x = "a__le";
Text[Style["Crossword Solver", Large]],
Text[Style["Enter the clue into the box, and see a list of possible answers appear!", Medium]],
Text[Style["Use _ to represent a missing letter", Medium ]],
"Clue " InputField[Dynamic[x], String, ContinuousAction -> True],
Dynamic["Possible Answers " Framed[Column[ReleaseHold[WolframAlpha[x,"WolframParse"]]]]]}]]
```
---/task---
