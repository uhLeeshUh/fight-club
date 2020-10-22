For tree structure visualization, it's helpful to think that the **dynamic value** as the node values. I.e. for today's problem, because the target string will be likely what is changing, that is what the node values will be. The array of strings will not change since we can use the elements as many times as we want.

Verbalize to your interviewer your thought process. Generally, it is helpful to almost "over-explain". In this problem, for example, verbalize to your interviewer that "Any empty string node in the tree signifies that there is a solution and that we should return true." and potentially also the inverse case, i.e. "We know there is no solution and should return false if there are no leaf nodes with the empty string".

In this particular problem, a potential issue could occur with our original diagram. If we take a string from the _middle_ of our target string, we end up putting two characters that aren't originally next to each other next to each other. _(i.e. canConstruct("abcd", ["a", "b", "ab", "cd", "ac"]), if we take "b" from the middle of the target string, "ac" could potentially be the next substring to subtract from our new target but we should not consider that to be a case)_ A solution to this is to only take from the beginning of the string ("prefix") or only take from the end of the string ("suffix"). 

In recursive solutions, it is common to potentially have both a bottom-up and a top-down solution. In this example, a top-down solution would be starting with the target node and subtracting down to an empty string case. A bottom-up solution would be starting with an empty string and building up to the target. (For the bottom-up solution, a potential solution would be continuously adding elements to the current value until we reach a length of larger or equal to the original target and then comparing the current value to the target string)