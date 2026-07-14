# Python Study Note: Finding the Runner-Up Score

## Challenge

Given a collection of participant scores, find the **runner-up score**, meaning the **second-highest unique score**.

### Example Input

```text
5
2 3 6 6 5
```

### Expected Output

```text
5
```

The highest score is `6`. Since duplicate scores do not count as separate rankings, the next unique score is `5`.

---

## Complete Code

```python
if __name__ == '__main__':

    # Read the number of scores from user input
    # int() converts the input from a string into an integer
    n = int(input())

    # Read the scores entered on one line
    # input() receives the entire line as a string
    # .split() separates the string at each space
    # map(int, ...) converts each separated value into an integer
    arr = map(int, input().split())

    # Convert the map object into a list
    # Example: [2, 3, 6, 6, 5]
    scores = list(arr)

    # Convert the list into a set
    # Sets automatically remove duplicate values
    # Example: {2, 3, 5, 6}
    unique_scores = set(scores)

    # Sort the unique values from lowest to highest
    # sorted() returns a new sorted list
    # Example: [2, 3, 5, 6]
    sorted_scores = sorted(unique_scores)

    # Use negative indexing to access the second-to-last value
    # -1 = last item (highest score)
    # -2 = second-to-last item (runner-up score)
    print(sorted_scores[-2])
```

---

## Step-by-Step Data Transformation

Starting scores:

```text
2 3 6 6 5
```

### Step 1: Convert Input Into a List

```python
scores = list(arr)
```

Result:

```text
[2, 3, 6, 6, 5]
```

A **list** maintains the collection of scores and allows duplicate values.

---

### Step 2: Remove Duplicates With a Set

```python
unique_scores = set(scores)
```

Result:

```text
{2, 3, 5, 6}
```

A **set** stores only unique values, so the duplicate `6` is removed.

This matters because the runner-up is the second-highest **unique** score.

---

### Step 3: Sort the Unique Scores

```python
sorted_scores = sorted(unique_scores)
```

Result:

```text
[2, 3, 5, 6]
```

The `sorted()` function arranges the values from lowest to highest and returns them as a new list.

---

### Step 4: Use Negative Indexing

```text
Positive index:   0   1   2   3
                  ↓   ↓   ↓   ↓
Values:          [2,  3,  5,  6]
                  ↑   ↑   ↑   ↑
Negative index:  -4  -3  -2  -1
```

Therefore:

```python
sorted_scores[-1]
```

returns the highest score:

```text
6
```

While:

```python
sorted_scores[-2]
```

returns the runner-up:

```text
5
```

---

## The Full Mental Model

```text
Raw input
    ↓
map()
    ↓
Convert to list
    ↓
Remove duplicates with set()
    ↓
Sort with sorted()
    ↓
Access second-to-last item with [-2]
    ↓
Print runner-up score
```

Or more simply:

```text
Input → Structure → Remove Duplicates → Sort → Select → Output
```

---

## Key Python Functions Used

| Function   | Purpose                               | Example                       |
| ---------- | ------------------------------------- | ----------------------------- |
| `input()`  | Receives user input as a string       | `"2 3 6 6 5"`                 |
| `.split()` | Splits a string into separate pieces  | `["2", "3", "6", "6", "5"]`   |
| `map()`    | Applies a function to every item      | Converts each string to `int` |
| `list()`   | Converts an iterable into a list      | `[2, 3, 6, 6, 5]`             |
| `set()`    | Creates a collection of unique values | `{2, 3, 5, 6}`                |
| `sorted()` | Returns values in sorted order        | `[2, 3, 5, 6]`                |
| `print()`  | Outputs the final result              | `5`                           |

---

## Important Syntax Lesson: `[arr]` vs `list(arr)`

These are **not the same thing**:

```python
scores = [arr]
```

This creates a list containing the entire `arr` object as **one element**:

```text
[<map object>]
```

But:

```python
scores = list(arr)
```

converts all the values from `arr` into individual list elements:

```text
[2, 3, 6, 6, 5]
```

This distinction was the cause of the original `IndexError`.

---

## Error Encountered: `IndexError: list index out of range`

The original code used:

```python
scores = [arr]
```

This meant the collection effectively had only one element. Later, the code attempted:

```python
sorted_scores[-2]
```

But Python cannot access the second-to-last element of a collection containing only one element.

The fix was:

```python
scores = list(arr)
```

---

## Big-O Connection

This solution also connects to algorithm complexity.

The major operations are approximately:

```text
list(arr)           → O(n)
set(scores)         → O(n) average
sorted(unique_scores) → O(k log k)
```

Where:

- `n` = total number of scores
- `k` = number of unique scores

Because sorting is the most expensive operation here, the overall time complexity is approximately:

```text
O(n + k log k)
```

If nearly every score is unique, then `k ≈ n`, giving us:

```text
O(n log n)
```

There is also an `O(n)` approach that finds the highest and second-highest unique values in a single pass without sorting. The current solution is simpler and more readable, while the single-pass approach is more efficient for very large datasets.

---

## Main Takeaways

1. A **list** stores ordered values and allows duplicates.
2. A **set** automatically removes duplicates.
3. `sorted()` returns values ordered from lowest to highest by default.
4. Negative indexing lets us access elements starting from the end of a sequence.
5. `[-1]` accesses the last element.
6. `[-2]` accesses the second-to-last element.
7. `[arr]` creates a list containing `arr` as one item, while `list(arr)` converts the contents of `arr` into individual list elements.
8. Before writing a manual loop, consider whether Python already provides a built-in function or data structure for the operation.

## Developer Perspective

A major part of becoming comfortable with Python is building your vocabulary of available tools. You may understand exactly what needs to happen logically—remove duplicates, sort values, find the second-highest score—but still not remember the exact function names.

That's normal during skill development. The goal isn't to memorize the entire Python standard library. The goal is to gradually recognize common patterns:

```text
Need unique values?       → set()
Need ordered values?      → sorted()
Need the largest value?   → max()
Need the smallest value?  → min()
Need to transform items?  → map()
Need to filter items?     → filter() or a comprehension
```

Over time, the gap between **"I know what I need to do"** and **"I know the Python syntax to do it"** gets smaller through repeated use.
