## Using Wolfram Alpha to analyse Iiput

Earlier you learned that to use `DictionaryLookup`, the input needs to be in a specific format:
+ Each letter has to be interpreted as a string, with `""`
+ Each blank space, `_`, needs to be its own expression; blank spaces cannot be strings
+ Each letter or blank space is separated by `~~`. 

It would be complicated to write code to format the input like this. Luckily, Wolfram has a tool that makes things easy for you. Using Wolfram Alpha's interpretation, you can take a string and run it through `DictionaryLookup` without having to format it.

Wolfram Alpha is a knowledge engine created using the Wolfram language. When you run a string through Wolfram Alpha, you get back a list of words that fit the pattern.

This is what you should recreate:

![wolfram alpha output](images/wolfram alpha.png)

With the command `"WolframParse"`, you can access the code that Wolfram Alpha runs.

![wolfram parse](images/wolframparse.png)

So when you run a string through Wolfram Alpha, it does a `DictionaryLookup`, just like you did at the beginning. But the code is on hold, because `HoldComplete` means that the code doesn't get evaluated yet (meaning it doesn't run yet). You can evaluate it by using `ReleaseHold`.

![release hold](images/releasehold.png)

Notice that `ReleaseHold[WolframAlpha["c_t_", "WolframParse"]]` and `DictionaryLookup["c" ~~ _ ~~ "t" ~~ _]` give the exact same output. You should use the `WolframAlpha` code. 

Now combine the `InputField` and the code calling Wolfram Alpha to translate the input into readable data for the `DictonaryLookup` function.

---task---
Use your `InputField` code, which uses `Dynamic`, to read the input. Then call Wolfram Alpha using `"WolframParse"` to find the words which match the pattern.

You  need to define a clue at the start of the code, so that the `InputField` is never empty.

```
x = "c_ts";

InputField[Dynamic[x], String, ContinuousAction -> True]

Dynamic[ReleaseHold[WolframAlpha[x, "WolframParse"]]]
 ```
---/task---

---task---

Type in different clues into the input box, and check to see that your program outputs a list of words that fit the clue.

---/task---
