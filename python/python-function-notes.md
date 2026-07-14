# Python Function Calls, Methods, and Arguments

## The Big Picture

A useful way to understand programming syntax is to read code as a structured instruction.

```text
Python: object → action → input
SQL:    action → target → condition
```

### Python Example

```python
scores.append(10)
```

Read it as:

> On the `scores` object → perform the `append` action → using `10` as the input.

```text
scores  →  append  →  10
object     action      input
```

### SQL Example

```sql
SELECT name
FROM users
WHERE id = 10;
```

Read it as:

> Perform the `SELECT` action → on the `users` target → where the condition is `id = 10`.

```text
SELECT  →  users  →  id = 10
action     target     condition
```

---

## Function vs. Method

A **function** stands on its own:

```python
print("Hello")
```

```text
print  →  "Hello"
function    argument
```

A **method** belongs to an object:

```python
scores.append(10)
```

```text
scores  →  append  →  10
object     method      argument
```

The dot `.` connects the object to a behavior that belongs to it.

---

## Creating a Custom Function

We can create our own function using the `def` keyword:

```python
def greet_user(name):
    print(f"Hello, {name}!")
```

Breakdown:

```text
def          → tells Python we are defining a function
greet_user   → the name of our function
name         → parameter that receives incoming data
```

At this point, we have **defined** the function, but we haven't executed it yet.

To call it:

```python
greet_user("Ulysses")
```

Output:

```text
Hello, Ulysses!
```

Read the function call aloud:

> Call the `greet_user` function and pass `"Ulysses"` as the argument.

```text
greet_user  →  "Ulysses"
function        argument
```

---

## Parameter vs. Argument

This distinction is small but important.

When defining the function:

```python
def greet_user(name):
```

`name` is the **parameter**. Think of it as a placeholder waiting to receive data.

When calling the function:

```python
greet_user("Ulysses")
```

`"Ulysses"` is the **argument**. It is the actual value being passed into the function.

```text
Definition:
def greet_user(name)
               ↑
           parameter

Function Call:
greet_user("Ulysses")
                ↑
             argument
```

A simple mental model:

```text
Parameter = empty parking space
Argument  = car that parks in that space
```

---

## Custom Function With a Return Value

Functions can also calculate something and send the result back:

```python
def add_numbers(a, b):
    return a + b
```

Call the function:

```python
result = add_numbers(5, 3)
print(result)
```

Output:

```text
8
```

The flow looks like this:

```text
5 ──→ a
        \
         → a + b → return 8
        /
3 ──→ b
```

Or more simply:

```text
Input → Function → Process → Return Value

5, 3 → add_numbers() → 5 + 3 → 8
```

---

## The Connection Across Technologies

The syntax changes between programming languages and technologies, but the underlying thinking often stays similar:

```text
Python Method:
object → action → input

scores → append → 10


Python Function:
action → input → result

add_numbers → 5, 3 → 8


SQL Query:
action → target → condition

SELECT → users → WHERE id = 10
```

The key takeaway is that code becomes easier to understand when you stop seeing it as symbols and start reading it as a set of instructions:

> **What am I working with? What action am I performing? What information am I giving it? What result should come back?**

That same thought process carries across Python, JavaScript, Java, APIs, databases, and eventually full software systems.
