## Building an interface

Your final job is to build an interface for your crossword solver.

You can alter your code from the previous task.

--- task ---
Use `Column` and `Framed` to put the possible words into a box.

```
x = "c_t";
InputField[Dynamic[x], String, ContinuousAction -> True]
Dynamic[
Framed[Column[ReleaseHold[WolframAlpha[x, "WolframParse"]]]]]
```
---/task ---

Can you see that your `InputField` and your results are two separate outputs? You can fix this by putting both pieces of code inside a `Column`. At the same time, you can add a title and instructions on how to use the tool.

--- task ---

+ Use what you know about `Column` and `Framed` to put both of your outputs into a single, framed column
+ Add text to label the `InputField` and the list of words
+ Use `Text` and `Style` to customise the look of the text

```
Framed[Column[{x = "a__le";
Text[Style["Crossword Solver", Large]],
"Clue " InputField[Dynamic[x], String, ContinuousAction -> True],
Dynamic["Possible Answers " Framed[Column[ReleaseHold[WolframAlpha[x,"WolframParse"]]]]]}]]
```
---/task---

--- task ---
Add  instructions for how to use your crossword solver to the framed column.

--- hints ---
--- hint ---
You need to add rows of text like the one that displays the title.
--- /hint ---
--- hint ---
Here are the text rows you should add:

```
Text[Style["Enter the clue into the box, and see a list of possible answers appear!", Medium]]
```

```
Text[Style["Use _ to represent a missing letter", Medium ]]
```
--- /hint ---
--- hint ---
The completed table code should look like this:

```
Framed[Column[{x = "a__le";
Text[Style["Crossword Solver", Large]],
Text[Style["Enter the clue into the box, and see a list of possible answers appear!", Medium]],
Text[Style["Use _ to represent a missing letter", Medium ]],
"Clue " InputField[Dynamic[x], String, ContinuousAction -> True],
Dynamic["Possible Answers " Framed[Column[ReleaseHold[WolframAlpha[x,"WolframParse"]]]]]}]]
```
--- /hint ---
--- /hints ---
--- /task ---