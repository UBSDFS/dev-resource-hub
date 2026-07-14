# Python Methods: With and Without Arguments

## The Basic Pattern

In Python, a method is a function that belongs to an object.

The general syntax is:

```python
object.method(argument)
```

A useful mental model is:

```text
object  →  method  →  argument
thing      action      input
```

Or even more simply:

```text
Python: object → action → input
SQL:    action → target → condition
```

---

## Example 1: Method That Takes an Argument

```python
# Create a list object
scores = [85, 90, 78]

# Call the append() method and pass 95 as the argument
scores.append(95)

# Print the updated list
print(scores)
```

### Output

```text
[85, 90, 78, 95]
```

### Breaking Down the Method Call

```python
scores.append(95)
```

```text
scores  →  append  →  95
object     method      argument
```

Read it aloud as:

> On the `scores` object, call the `append` method and pass `95` as the argument.

The `append()` method needs input because Python needs to know **what value should be added to the list**.

```text
Object:    scores
Method:    append()
Argument:  95
```

---

## Example 2: Method That Takes No Argument

```python
# Create a string object
name = "ulysses"

# Call the capitalize() method
formatted_name = name.capitalize()

# Print the result
print(formatted_name)
```

### Output

```text
Ulysses
```

### Breaking Down the Method Call

```python
name.capitalize()
```

```text
name  →  capitalize  →  no argument needed
object     method
```

Read it aloud as:

> On the `name` object, call the `capitalize` method.

No argument is needed because the method already knows what data to work with: the `name` object itself.

```text
Object:    name
Method:    capitalize()
Argument:  None needed
```

---

## Side-by-Side Comparison

```python
scores.append(95)       # Method takes an argument

name.capitalize()       # Method takes no argument
```

Visually:

```text
WITH AN ARGUMENT

scores  →  append  →  95
object     action      input


WITHOUT AN ARGUMENT

name  →  capitalize
object     action
```

The parentheses `()` are still required to call the method, even when no argument is passed:

```python
name.capitalize()
```

The empty parentheses mean:

> Call this method, but I don't need to provide it with any additional input.

---

## Key Takeaway

```text
object.method(argument)
   ↓      ↓       ↓
 thing   action   input
```

Not every method requires an argument:

```python
scores.append(95)     # Needs input: What should be added?

name.capitalize()     # No input needed: It operates on the object itself.
```

When reading a method call, ask three questions:

1. **What object am I working with?**
2. **What action am I asking it to perform?**
3. **Does it need additional input to perform that action?**

This gives you a simple way to read and trace method calls instead of trying to memorize syntax.
