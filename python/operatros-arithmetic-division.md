# Python Division Operators: `/`, `//`, and `%`

## Lesson Overview

Python provides different division operators depending on the type of result needed.

```python
a = 7
b = 2

print(a / b)   # 3.5
print(a // b)  # 3
print(a % b)   # 1
```

## Regular Division `/`

The `/` operator performs standard division and returns the full result, including the decimal value.

```python
print(7 / 2)
# Output: 3.5
```

**Think:** What is the complete mathematical result?

---

## Floor Division `//`

The `//` operator performs floor division. Floor means to **round down** to the nearest whole number.

```python
print(7 // 2)
# Output: 3
```

Although `7 / 2` equals `3.5`, floor division rounds the result down to `3`.

**Think:** How many complete whole groups fit?

### Practical Example

If 17 people are divided into groups of 4:

```python
people = 17
group_size = 4

full_groups = people // group_size

print(full_groups)
# Output: 4
```

Four complete groups can be created.

---

## Modulo `%`

The modulo operator returns the remainder left after division.

```python
print(17 % 4)
# Output: 1
```

After creating four complete groups of four, one person remains.

---

## Floor vs. Ceiling

Floor rounds **down**, while ceiling rounds **up**.

```python
import math

print(math.floor(3.5))  # 3
print(math.ceil(3.5))   # 4
```

Visual reminder:

```text
4   ← Ceiling: round up
3.5 ← Original value
3   ← Floor: round down
```

## Quick Reference

| Operator or Function | Purpose                              | Example           | Result |
| -------------------- | ------------------------------------ | ----------------- | -----: |
| `/`                  | Returns the complete division result | `7 / 2`           |  `3.5` |
| `//`                 | Floor division: rounds down          | `7 // 2`          |    `3` |
| `%`                  | Returns the remainder                | `7 % 2`           |    `1` |
| `math.floor()`       | Rounds a value down                  | `math.floor(3.5)` |    `3` |
| `math.ceil()`        | Rounds a value up                    | `math.ceil(3.5)`  |    `4` |

## Key Takeaway

```text
/  → Give me the complete division result.
// → Tell me how many complete whole groups fit.
%  → Tell me what is left over.

Floor   → Round down ⬇️
Ceiling → Round up ⬆️
```

The syntax may change between programming languages, but the underlying concepts remain the same.
