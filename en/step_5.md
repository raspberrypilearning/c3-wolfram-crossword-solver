## Combining Input Fields and Wolfram Alpha Code

Now we can combine the `InputField` and our code calling Wolfram Alpha to translate the input into readable data for the `DictonaryLookup` function.

---task---

Use your `InputField` code, which uses `Dynamic`, to read the input, and then use your code to call Wolfram Alpha using `"WolframParse"` to find the words which match the pattern.

You will need to define a clue at the start of your code, so that the `InputField` is never empty.

```
x = "c_ts";

InputField[Dynamic[x], String, ContinuousAction -> True]

Dynamic[ReleaseHold[WolframAlpha[x, "WolframParse"]]]
 ```
---/task---

---task---

Try typing different clues into the input box, and check to see that your code is outputting a list of feasible words.

---/task---
