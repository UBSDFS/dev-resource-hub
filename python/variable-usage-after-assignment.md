# Variables After Assignment

## Concept

Once a variable has been assigned a value, Python remembers both the value and its data type.

Example:

```python
a = int(input())
b = int(input())
```

This statement performs three operations:

1. Waits for user input.
2. Converts the input from a string to an integer.
3. Stores the integer in the variable.

If the user enters:

```
3
2
```

Python is effectively working with:

```python
a = 3
b = 2
```

From this point forward, `a` and `b` behave exactly like normal integers.

---

## Using the Variables

Once assigned, use the variable names—not the original values.

```python
print(a + b)
print(a - b)
print(a * b)
```

Python substitutes the stored values automatically.

For the example above, Python evaluates:

```python
print(3 + 2)
print(3 - 2)
print(3 * 2)
```

Output:

```
5
1
6
```

---

## Common Beginner Mistake

❌ Hard-coding the example input:

```python
print(3 + 2)
```

This only works if the input is actually `3` and `2`.

✔ Correct:

```python
print(a + b)
```

Using variables allows the program to work for **any** valid input.

---

## Key Takeaway

Think of a variable as a labeled container.

```text
User Input
     │
     ▼
int(input())
     │
     ▼
Variable (a)
     │
     ▼
Use `a` anywhere you need that value
```

Once the value is stored, you no longer need to know what the user typed—you simply work with the variable.

---

## Rule of Thumb

> **Assign once. Use many times.**

A variable stores both the value and its data type until it is reassigned.

---

## Concepts Reinforced

- Variables
- Assignment (`=`)
- User input (`input()`)
- Type conversion (`int()`)
- Arithmetic operators (`+`, `-`, `*`)
- Using variables instead of hard-coded values
- Writing reusable code
