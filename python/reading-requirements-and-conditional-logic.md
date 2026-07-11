# Reading Requirements and Translating Them Into Code

## Lesson Overview

One of the biggest lessons from working through coding challenges is that knowing the syntax is only part of solving the problem.

The other part is learning how to:

- Read the requirements carefully.
- Identify important keywords.
- Determine the input and expected output.
- Recognize boundaries and conditions.
- Identify exceptions to rules.
- Translate the requirements into code.

Sometimes the problem tells you exactly what to do, but the instructions are written using variables, mathematical expressions, or words that change the logic.

---

## Example: Understanding the Leap Year Problem

The leap year rules are:

1. If a year is evenly divisible by `4`, it is a leap year.
2. **Unless** it is also evenly divisible by `100`, then it is not a leap year.
3. **Unless** it is also evenly divisible by `400`, then it is a leap year.

The most important word in this problem is:

> **Unless**

The word `unless` tells us that there is an exception to the previous rule.

The logic can be simplified to:

```text
Divisible by 400 → Leap year
Divisible by 100 → Not a leap year
Divisible by 4   → Leap year
Otherwise        → Not a leap year
```

Important Words to Look For

Certain words in coding problems provide clues about the logic you may need.

Word or Phrase Possible Meaning
unless Exception to a previous rule
except Exclusion or special case
and Multiple conditions must be true
or At least one condition must be true
at least >=
at most <=
greater than >
less than <
exactly ==
for all Possible loop
each / every Possible loop
evenly divisible Modulo %
remainder Modulo %
complete groups Floor division //
