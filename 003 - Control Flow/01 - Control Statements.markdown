So far, our Python programs have run line by line, top to bottom, always producing the same result. **Control flow** lets programs make decisions and take different paths based on conditions, like choosing between two roads at a fork. This introduces logic, making programs more dynamic and interactive.

# If Statement

An **if statement** checks a condition:

- If the condition is `True`, it runs the code inside the `if` block.
- If the condition is `False`, it skips the code.
- Syntax:
    
    ```python
    if condition:
        # Code here (indented, usually 2 spaces)
    ```
    

**Example**:

```python
grade = 75
if grade > 60:
    print("You passed!")  # Output: You passed!
```

- The condition `grade > 60` is `True`, so the message prints.
- Indentation is crucial to show which code belongs to the `if`.

# Else Clause

An **else** clause runs when the `if` condition is `False`:

- Syntax:
    
    ```python
    if condition:
        # Code if True
    else:
        # Code if False
    ```
    

**Example**:

```python
grade = 50
if grade > 60:
    print("You passed.")
else:
    print("You failed.")  # Output: You failed.
```

- Since `grade > 60` is `False`, the `else` block runs.

# Elif Clause

An **elif** (short for "else if") checks additional conditions if the previous ones are `False`. Only one block (`if`, `elif`, or `else`) runs.

- Syntax:
    
    ```python
    if condition1:
        # Code
    elif condition2:
        # Code
    else:
        # Code
    ```
    

**Example**:

```python
grade = 85
if grade > 90:
    print('A')
elif grade > 80:
    print('B')  # Output: B
elif grade > 70:
    print('C')
elif grade > 60:
    print('D')
else:
    print('F')
```

- Checks conditions in order; stops at the first `True` condition (`grade > 80`).

# Relational Operators

Conditions often compare values using **relational operators**:

- `==`: Equal to
- `!=`: Not equal to
- `>`: Greater than
- `<`: Less than
- `>=`: Greater than or equal to
- `<=`: Less than or equal to

**Example**:

```python
age = 18
if age >= 18:
    print("You can vote!")  # Output: You can vote!
```

---

# Coin Flip Program (`coin_flip.py`)

This program simulates a coin toss using control flow to show how programs can produce different outcomes.

**Code**:

```python
import random
num = random.randint(0, 1)  # Randomly picks 0 or 1
if num > 0.5:
    print('Heads')
else:
    print('Tails')
```

**How It Works**:

- `random.randint(0, 1)` generates either `0` or `1`.
- If `num > 0.5` (i.e., `num` is `1`), prints "Heads".
- Otherwise, prints "Tails".
- About 50% chance for each outcome.
- **Run it 5 times**: You might get a mix (e.g., 3 Heads, 2 Tails), as it’s random.

**Tip**: The `random` module will be covered later; for now, know it adds unpredictability.

---

# Grades Program (`grades.py`)

This program checks if a grade passes or fails based on a threshold.

**Task**:

- Create a variable `grade` (0–100).
- Use `if`/`else` to print:
    - "You passed." if `grade >= 55`.
    - "You failed." otherwise.

**Code**:

```python
grade = 70
if grade >= 55:
    print("You passed.")  # Output: You passed.
else:
    print("You failed.")
```

**How It Works**:

- Tests `grade >= 55`.
- For `grade = 70`, it’s `True`, so prints "You passed.".
- Try different values (e.g., `grade = 50` prints "You failed.").

**Testing Tip**:

- Change `grade` to values like `55`, `54`, `80`, and `30` to confirm the logic works.

---

# pH Levels Program (`ph_levels.py`)

This program determines if a pH level is acidic, basic, or neutral using `if`/`elif`/`else`.

**Task**:

- Create a `ph` variable by asking the user for a value (0–14).
- Output:
    - "Basic" if `ph > 7`.
    - "Acidic" if `ph < 7`.
    - "Neutral" if `ph == 7`.

**Code**:

```python
ph = float(input("Enter pH level (0-14): "))
if ph > 7:
    print("Basic")
elif ph < 7:
    print("Acidic")
else:
    print("Neutral")
```

**How It Works**:

- `input()` gets the pH as a string; `float()` allows decimals (e.g., 7.5).
- Checks conditions in order:
    - `ph > 7`: Basic (e.g., `ph = 8` → "Basic").
    - `ph < 7`: Acidic (e.g., `ph = 6` → "Acidic").
    - Otherwise: Neutral (e.g., `ph = 7` → "Neutral").

**Example Runs**:

```
Enter pH level (0-14): 8
Basic
Enter pH level (0-14): 7
Neutral
Enter pH level (0-14): 4
Acidic
```

---

### Additional Notes

- **Why Control Flow?**:
    - It’s like giving your program a brain to choose actions based on situations.
    - Used in games (e.g., if health < 0, game over) or apps (e.g., if user logged in, show profile).
- **Indentation**:
    - Python uses indentation (2 or 4 spaces) to group code in `if`/`elif`/`else` blocks.
    - Wrong indentation causes errors:
        
        ```python
        if grade > 60:
        print("Error!")  # IndentationError
        ```
        
- **Only One Path Runs**:
    - In an `if`/`elif`/`else` chain, only the first `True` condition’s block executes.
    - Example: If `grade = 95`, only `A` prints, even if `grade > 80` is also `True`.
- **Improving Programs**:
    - **Coin Flip**: Add a loop to flip multiple times:
        
        ```python
        import random
        for _ in range(5):
            num = random.randint(0, 1)
            if num > 0.5:
                print('Heads')
            else:
                print('Tails')
        ```
        
    - **Grades**: Validate input:
        
        ```python
        grade = int(input("Enter grade (0-100): "))
        if 0 <= grade <= 100:
            if grade >= 55:
                print("You passed.")
            else:
                print("You failed.")
        else:
            print("Invalid grade!")
        ```
        
    - **pH Levels**: Handle invalid inputs:
        
        ```python
        try:
            ph = float(input("Enter pH level (0-14): "))
            if 0 <= ph <= 14:
                if ph > 7:
                    print("Basic")
                elif ph < 7:
                    print("Acidic")
                else:
                    print("Neutral")
            else:
                print("pH must be between 0 and 14.")
        except ValueError:
            print("Please enter a valid number!")
        ```
        
- **Relational Operators in Action**:
    - Combine with math: `if (x ** 2) > 100: print("Big number!")`.
    - Test equality carefully: `==` checks value, not type (e.g., `5 == 5.0` is `True`).
- **Random Note**:
    - `random.randint(0, 1)` picks a whole number between 0 and 1 (inclusive).
    - For coin flips, `num > 0.5` treats `1` as Heads, `0` as Tails.

---

### Tips for Beginners

- Think of `if`/`else` as a yes/no question: "Is grade > 60? Yes → Pass, No → Fail."
- Write conditions clearly using `==`, `>`, etc., to avoid confusion.
- Test programs with different inputs (e.g., `ph = 7`, `8`, `6`) to see all paths.
- Keep indentation consistent—use 2 spaces or let editors handle it.
- Start small: Write one `if`, test it, then add `elif` or `else`.
- Have fun with randomness! Try the coin flip to see how outcomes vary.