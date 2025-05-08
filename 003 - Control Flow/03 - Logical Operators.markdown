**Logical operators** (also called Boolean operators) combine conditions to make decisions in programs. They evaluate whether conditions are `True` or `False`, allowing more complex logic in control flow. Python has three logical operators: `and`, `or`, and `not`.

### 1. `and` Operator

- **What it does**: Returns `True` only if **both** conditions are `True`; otherwise, returns `False`.
- **Example**:
    
    ```python
    hunger = 5
    anger = 2
    if hunger > 4 and anger > 1:
        print('Hangry')  # Output: Hangry
    ```
    
    - Both `hunger > 4` (`True`) and `anger > 1` (`True`) must be `True` to print "Hangry".
    - If either is `False` (e.g., `anger = 0`), nothing prints.

### 2. `or` Operator

- **What it does**: Returns `True` if **at least one** condition is `True`; returns `False` only if both are `False`.
- **Example**:
    
    ```python
    coffee = 1
    bubble_tea = 0
    if coffee > 0 or bubble_tea > 0:
        print('😊')  # Output: 😊
    ```
    
    - Only one condition needs to be `True` (here, `coffee > 0` is `True`, so it prints).
    - If both are `False` (e.g., `coffee = 0`, `bubble_tea = 0`), nothing prints.

### 3. `not` Operator

- **What it does**: Reverses a condition’s truth value (`True` becomes `False`, and vice versa).
- **Example**:
    
    ```python
    tired = False
    if not tired:
        print('Time to code!')  # Output: Time to code!
    ```
    
    - `not tired` checks if `tired` is `False`. Since it is, the condition is `True`, so it prints.
    - If `tired = True`, `not tired` is `False`, and nothing prints.

### Truth Table for `and` and `or`

To clarify the difference between `and` and `or`:

| A | B | A and B | A or B |
| --- | --- | --- | --- |
| False | False | False | False |
| False | True | False | True |
| True | False | False | True |
| True | True | True | True |
- **and**: Needs **both** `A` and `B` to be `True` to return `True`.
- **or**: Needs **either** `A` or `B` to be `True` to return `True`.

---

### The Cyclone Program (`the_cyclone.py`)

The Cyclone is a roller coaster at Coney Island, Brooklyn, with a **height requirement** of 137 cm and a **cost** of 10 credits. This program checks if a user can ride based on their height and credits.

**Task**:

- Ask the user for their height (in cm) and credits.
- Use logical operators to check:
    - If tall enough (height ≥ 137) **and** have enough credits (credits ≥ 10), print "Enjoy the ride!"
    - If enough credits but not tall enough, print "You are not tall enough to ride."
    - If tall enough but not enough credits, print "You don't have enough credits."
    - Otherwise, print a message saying neither requirement is met.

**Code**:

```python
height = float(input("Enter your height in cm: "))
credits = float(input("Enter your credits: "))

if height >= 137 and credits >= 10:
    print("Enjoy the ride!")
elif credits >= 10:
    print("You are not tall enough to ride.")
elif height >= 137:
    print("You don't have enough credits.")
else:
    print("You don't meet the height or credits requirement.")
```

**How It Works**:

1. `input()` gets height and credits; `float()` allows decimals for flexibility.
2. Checks conditions in order:
    - `height >= 137 and credits >= 10`: Both must be `True` to ride.
    - `elif credits >= 10`: If the first condition fails but credits are enough, height must be too low.
    - `elif height >= 137`: If credits aren’t enough but height is, credits are the issue.
    - `else`: Neither condition is met.
3. Only one message prints based on the first `True` condition.

**Example Runs**:

```
Enter your height in cm: 140
Enter your credits: 12
Enjoy the ride!
```

```
Enter your height in cm: 130
Enter your credits: 15
You are not tall enough to ride.
```

```
Enter your height in cm: 150
Enter your credits: 5
You don't have enough credits.
```

```
Enter your height in cm: 120
Enter your credits: 3
You don't meet the height or credits requirement.
```

---

### Additional Notes

- **Why Logical Operators?**:
    - They let you combine multiple conditions, like needing **both** height and credits for the Cyclone.
    - Used in real-world apps (e.g., if user is logged in **and** has permission, show data).
- **Order Matters**:
    - Check the most specific condition first (e.g., `height >= 137 and credits >= 10`).
    - `elif` clauses catch remaining cases, and `else` handles everything else.
    - Example: If you check `height >= 137` first, you might miss the credits check.
- **Improving the Program**:
    - Add input validation:
        
        ```python
        try:
            height = float(input("Enter your height in cm: "))
            credits = float(input("Enter your credits: "))
            if height < 0 or credits < 0:
                print("Height and credits must be non-negative.")
            elif height >= 137 and credits >= 10:
                print("Enjoy the ride!")
            elif credits >= 10:
                print("You are not tall enough to ride.")
            elif height >= 137:
                print("You don't have enough credits.")
            else:
                print("You don't meet the height or credits requirement.")
        except ValueError:
            print("Please enter valid numbers!")
        ```
        
    - This prevents crashes from non-numeric inputs and ensures realistic values.
- **Common Errors**:
    - **SyntaxError**: Forgetting colons `:` or indentation in `if`/`elif`/`else`.
    - **TypeError**: Comparing strings with numbers (use `float()` or `int()` for inputs).
    - **Logic Error**: Wrong operator (e.g., `or` instead of `and` changes the logic).
- **Combining Operators**:
    - Mix logical and relational operators:
        
        ```python
        age = 16
        has_ticket = True
        if age >= 13 and has_ticket:
            print("Welcome to the movie!")  # Output: Welcome to the movie!
        ```
        
- **Not Operator Use Case**:
    - Simplify conditions:
        
        ```python
        is_raining = False
        if not is_raining:
            print("Go outside!")  # Output: Go outside!
        ```
        

---

### Tips for Beginners

- Think of `and` as "both must be true" and `or` as "at least one is true."
- Test `not` with simple conditions: `not False` is `True`, `not True` is `False`.
- Write out conditions in plain English first: "If tall enough AND enough credits, ride."
- Test all paths in your program (e.g., try `height = 137`, `credits = 10`, then `height = 136`).
- Use `print()` to debug conditions: `print(height >= 137, credits >= 10)` shows what’s `True` or `False`.
- Keep practicing—logical operators make your programs smarter!