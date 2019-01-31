```
Column[{x = "a__le";
  Text[Style["Crossword Solver", Large]],
  Text[Style[
    "Enter the clue into the box, and see a list of possible answers appear!", Medium]],
  Text[Style["Use _ to represent a missing letter", Medium ]],
  "Clue " InputField[Dynamic[x], String, ContinuousAction -> True], 
  Dynamic[
   "Possible Answers " Column[
     ReleaseHold[WolframAlpha[x, "WolframParse"]], Frame -> True]]}, 
 Frame -> True]
 ```