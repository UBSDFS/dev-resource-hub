# Topic

Python Conditionals

## Difficulty

🟢 Beginner

## Prerequisites

- Variables
- User Input
- Integers

## Concepts

- if
- elif
- else
- %
- range()
- Boolean Logic
- Membership Operator (`in`)

## Overview

Conditional statements allow a program to make decisions by evaluating whether an expression is `True` or `False`. They are one of the core building blocks of programming and are commonly used to control program flow.

---

## Syntax

```python
if condition:
    # Executes if the condition is True

elif another_condition:
    # Executes if the previous condition was False
    # and this condition is True

else:
    # Executes if none of the above conditions are True
```

---

## Example

```python
n = int(input())

if n % 2 != 0:
    print("Weird")
elif n % 2 == 0 and n in range(2, 6):
    print("Not Weird")
elif n % 2 == 0 and n in range(6, 21):
    print("Weird")
else:
    print("Not Weird")
```

---

## Code Walkthrough

### 1. Check if the number is odd

```python
if n % 2 != 0:
```

The modulus (`%`) operator returns the remainder after division.

Example:

```python
7 % 2   # 1
8 % 2   # 0
```

If the remainder is **not** zero, the number is odd.

---

### 2. Check if the number is even and between 2–5

```python
elif n % 2 == 0 and n in range(2, 6):
```

This condition combines two Boolean expressions using the `and` operator.

Both conditions must evaluate to `True`.

- `n % 2 == 0` → Number is even
- `n in range(2, 6)` → Number is 2, 3, 4, or 5

---

### 3. Check if the number is even and between 6–20

```python
elif n % 2 == 0 and n in range(6, 21):
```

Python's `range()` includes the starting value but excludes the ending value.

```python
range(6, 21)
```

Contains:

```
6, 7, 8, ..., 20
```

---

### 4. Everything else

```python
else:
```

If none of the previous conditions evaluate to `True`, the remaining possibility is an even number greater than 20.

---

# Concepts Learned

## Modulus Operator (`%`)

Used to determine whether a number is odd or even.

```python
n % 2 == 0     # Even

n % 2 != 0     # Odd
```

---

## Comparison Operators

```python
==      Equal to

!=      Not equal to

>       Greater than

<       Less than

>=      Greater than or equal to

<=      Less than or equal to
```

---

## Boolean Operators

Python uses Boolean operators to combine expressions.

```python
and

or

not
```

Example:

```python
age >= 18 and has_license
```

Both conditions must be true.

---

## Membership Operator

```python
in
```

Checks whether a value exists inside a sequence.

Example:

```python
n in range(2, 6)
```

---

## The `range()` Function

Syntax:

```python
range(start, stop)
```

The start value is included.

The stop value is excluded.

Example:

```python
range(1, 5)
```

Produces:

```
1, 2, 3, 4
```

---

# Common Mistakes

❌ Forgetting the colon (`:`)

```python
if condition
```

✔ Correct

```python
if condition:
```

---

❌ Incorrect indentation

Python uses indentation to define code blocks.

```python
if condition:
print("Hello")
```

✔ Correct

```python
if condition:
    print("Hello")
```

---

❌ Forgetting quotation marks

```python
print(Weird)
```

✔ Correct

```python
print("Weird")
```

---

❌ Forgetting that `range()` excludes the ending value

```python
range(6, 20)
```

Stops at **19**, not 20.

---

# Personal Notes

### What I learned

- Break the problem into plain English before writing code.
- Build the logic first and worry about syntax second.
- Python relies heavily on indentation.
- `range()` excludes the ending value.
- `%` is commonly used for odd/even checks.
- Boolean operators (`and`, `or`, `not`) allow multiple conditions to be evaluated together.
- Reading code aloud often helps identify logic errors.

---

# Possible Refactor

Once execution reaches the `elif` statements, Python already knows the number is **not odd**, making the even check redundant.

Original:

```python
elif n % 2 == 0 and n in range(2, 6):
```

Refactored:

```python
elif n in range(2, 6):
```

This produces the same result while making the code slightly cleaner.
