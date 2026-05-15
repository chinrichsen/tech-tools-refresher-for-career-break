# Day 1 – Core Python basics

Welcome to **Day 1** of the 21‑Day Python & Pandas refresher.

This is **not** a beginner‑from‑zero course.  
The goal is to **reactivate** your Python fluency for data work, not to relearn the entire language.

By the end of this day, you should feel comfortable again with:
- variables, types, and simple expressions,  
- lists and dictionaries,  
- `for` loops and `if` / `else`,  
- basic functions and f‑strings,  
so you can focus on **thinking**, not syntax, in the Pandas days that follow.

---

## What you’ll rebuild today

You’ll practice the **building blocks** of Python that underlie almost all data‑related scripts:

- Variables and basic types (`int`, `float`, `str`, `bool`, `None`).  
- Simple containers: **lists** and **dictionaries**.  
- Looping with `for`.  
- Making decisions with `if` / `elif` / `else`.  
- Writing small reusable functions.  
- Using f‑strings for clean output and debugging.  

These are the same pieces you’ll later use inside Pandas workflows (e.g., during data cleaning, feature creation, or post‑processing).

---

## Why this matters for a “returning” refresher

After a career gap, many people remember concepts but lose **speed and muscle memory**.  
Exercises feel slower, syntax misfires more often, and that delay can feel like “I’ve forgotten everything” in an interview, even when you technically still know the language.

Day 1 is designed to:

- Re‑establish **routine patterns** with minimal pressure.  
- Help you notice **what feels rusty** so you can target it later.  
- Build a small “win” you can talk about on LinkedIn or in an interview.

Think of this day as **re‑tuning the instrument**, not re‑learning music.

---

## Core concepts (with small code examples)

### 1. Variables and basic types

You’ll refresh **variable assignment** and **primitive types**.

#### What is a variable?

A **variable** is a named “container” that holds a value you can refer to later in your code.  
It lets you give a name to data so you don’t have to write the same value repeatedly.

Example:

```python
name = "Carlos"
years_away = 3
active_again = True
```

Here:
- `name` is a **variable** holding a string.
- `years_away` is a **variable** holding an integer.
- `active_again` is a **variable** holding a boolean.

#### What are basic types?

Python uses several **built‑in types** that you’ll see constantly in data work:

- `int` – whole numbers like `3`, `123`, `-10`.  
- `float` – decimal numbers like `3.14`, `12.5`, `-0.01`.  
- `str` – text, like `"Carlos"` or `"Python"`.  
- `bool` – boolean values: `True` or `False`.  
- `None` – a special value meaning “no value” or “missing”.

Understanding these types is important because later, when you clean data in Pandas, you’ll often change a column’s type from `object` to `float` or `int`, and this is the same idea at the value level.

---

### 2. Lists and dictionaries

You’ll reactivate **containers**: **lists** and **dictionaries**.

#### What is a list?

A **list** is an **ordered collection** of items.  
You can store numbers, strings, or even mixed types.  
Lists are written with square brackets:

```python
prices = [12.5, 8.0, 19.99, 5.5]
```

Lists are useful because:
- They keep values in a specific order.  
- You can add, remove, or access items by their **position** (index).

#### What is a dictionary?

A **dictionary** is an **unordered** collection of **key‑value pairs**.  
You use it when you want to label data: for example, `"name": "Notebook"`.

```python
product = {
    "name": "Notebook",
    "price": 12.5,
    "in_stock": True
}
```

Dictionaries are useful because:
- They let you organize related data under meaningful names.  
- They are the natural “row‑level” structure you’ll later build into DataFrames.

---

### 3. Loops and conditionals

You’ll re‑practice **loops** and **conditionals**.

#### What is a loop?

A **loop** is a way to repeat a block of code multiple times.  
In Python, `for` is the most common loop for iterating over sequences like lists.

Example:

```python
prices = [12.5, 8.0, 19.99, 5.5]

for price in prices:
    if price >= 10:
        print(f"{price} is expensive")
    else:
        print(f"{price} is affordable")
```

Here, `for price in prices:` **loops** over each element in the `prices` list.  
The indented block under `for` runs once for each value.

**Why loops are useful:**

- They let you perform the same operation on many items at once.  
- This is the mental model behind many Pandas operations, like applying a function across a Series or DataFrame column.

#### What are conditionals?

A **conditional** is a way to choose between different paths in your code based on some condition.  
In Python, this is done with `if`, `elif`, and `else`.

Example:

```python
price = 12

if price >= 20:
    print("Very expensive")
elif price >= 10:
    print("Expensive")
else:
    print("Affordable")
```

**Why conditionals are useful:**

- They let you branch logic based on data values.  
- This pattern maps naturally to creating **new columns** in Pandas, such as segmenting customers or flagging certain records.

---

### 4. Writing small functions

You’ll refresh **functions**, which are reusable blocks of code.

#### What is a function?

A **function** is a named block of code that can be executed **later** with different inputs.  
It lets you **factor out** repeated logic so you don’t copy‑paste the same code.

In Python, functions are defined with `def` and can take arguments and return a value.

Example:

```python
def classify_price(price):
    if price >= 15:
        return "high"
    elif price >= 10:
        return "medium"
    else:
        return "low"
```

Here:
- `classify_price` is the **name** of the function.  
- `price` is an **argument** (input).  
- The `return` statements define the **output**.

You can then reuse it:

```python
classify_price(8)
classify_price(12)
classify_price(20)
```

**Why functions are useful:**

- They make code **testable** and **modular**.  
- Later, you’ll write functions that run inside `.apply` or custom aggregations, so this pattern is important for data‑analysis workflows.

---

### 5. Mini synthetic data pattern

Toward the end of the day, you’ll see a tiny example of **synthetic transaction‑style data**, which will later evolve into full DataFrames.

#### What is synthetic data?

**Synthetic data** is data that you **generate in code** rather than read from a file or database.  
It’s useful for learning because:
- You control the shape and content.  
- You can make it as simple or messy as needed.  
- You can repeat it without external dependencies.

Example structure:

```python
transactions = [
    {"item": "Book", "amount": 15},
    {"item": "Pen", "amount": 3},
    {"item": "Bag", "amount": 45}
]
```

This is a **list of dictionaries**.  
Each dictionary represents a record with named fields (`item`, `amount`), which is the same structure you’ll later see behind Pandas DataFrames.

You’ll not write the full exercises here; those live in `exercises.ipynb`.  
The goal in this `README` is to **show the pattern** and **put names on the concepts**, not to repeat the problem set.

---

## Structure of Day 1 in this folder

This folder contains:

- `lesson.ipynb`  
  5–10 minutes of concept review plus 2 worked examples that show the patterns above.

- `exercises.ipynb`  
  3–5 practice problems that ask you to:
  - Create and inspect variables, lists, and dictionaries.
  - Write simple loops and conditionals.
  - Define small functions.
  - Process a small list of synthetic “records”.

- `solutions.ipynb`  
  Complete answers with explanations for every exercise.

- `reflection.md` (template)  
  Short prompts to help you:
  - Note what felt rusty.
  - Note what clicked.
  - Draft a short LinkedIn‑style post idea.

Your task for the day is to:
1. Read `lesson.ipynb` and run the examples.  
2. Attempt `exercises.ipynb` **without** immediately peeking at `solutions.ipynb`.  
3. Use `solutions.ipynb` to compare and learn, not just to copy.  
4. Fill in `reflection.md` so you can later reuse the wording for LinkedIn or conversation.

---

## Reflection prompts (for your `reflection.md`)

Answer these in your own words:

1. **What felt rusty?**  
   Which syntax or pattern surprised you with how long it took to come back?

2. **What felt easier than expected?**  
   Was there anything that “just flowed” again?

3. **What would you want to review tomorrow?**  
   Is there one concept you’d repeat first?

4. **LinkedIn post idea (1–2 sentences)**  
   Example starter:  
   > “Day 1 of my 21‑day Python refresher is done. Today I rebuilt basic fluency with variables, loops, dictionaries, and functions—the simple things that become powerful once you start using them again.”

You can keep this version or tweak it into your own voice.

---

## How to think about Day 1

- **Do not** treat this as a “test.”  
- **Do** treat it as a **rhythm‑building** day.  
- If you forget a symbol or a keyword, that’s normal; the goal is to **re‑expose yourself** to the patterns quickly and repeatedly.

If you find yourself staring at a problem for more than 3–5 minutes, it’s okay to:
- check the `solutions.ipynb` for a hint,  
- or ask me to walk through a specific pattern,  
because Day 1 is about **re‑starting**, not about perfection.

---

## Next step in the 21‑day plan

After Day 1, the next days will:
- Reinforce **control flow** and error handling.  
- Deepen **functions and modules**.  
- Then move into **NumPy and Pandas**, using the same Python you just re‑activated.

By the time you reach the Pandas notebooks, the syntax will be second‑nature again, and you can focus on **data‑thinking**, not language‑thinking.

---

# Day 1 commitment

**Estimated time: 30–45 minutes**  
Commit only to that today.  
Build momentum, not exhaustion.  
Then come back tomorrow for Day 2: Control flow and error handling.