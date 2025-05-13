As programs grow more complex, you may need to check additional conditions after one condition is already true. **Nested if statements** allow you to place an `if` statement inside another `if` statement, creating layered decision-making. This is like making a decision, then asking a follow-up question based on the first answer.

### What Are Nested If Statements?

- A **nested if statement** is an `if` (or `if`/`elif`/`else`) block inside another `if` block.
- The inner `if` only runs if the outer `if` condition is `True`.
- **Indentation** is critical in Python—it shows which code belongs to which block.

**Basic Example**:

```python
age = 20
if age >= 18:
    print('You are old enough to apply for a loan.')
else:
    print('You are too young to apply for a loan.')
```

**Nested Example**:

```python
age = 20
income = 25000
if age >= 18:
    if income >= 20000:
        print('You are eligible for a loan.')  # Output: You are eligible for a loan.
    else:
        print('Your income is too low to be eligible for a loan.')
else:
    print('You are too young to apply for a loan.')
```

**How It Works**:

1. **Outer `if`**: Checks `age >= 18`.
    - If `True` (e.g., `age = 20`), moves to the inner `if`.
    - If `False` (e.g., `age = 16`), prints "You are too young..." and skips the inner block.
2. **Inner `if`**: Checks `income >= 20000`.
    - If `True` (e.g., `income = 25000`), prints "You are eligible...".
    - If `False` (e.g., `income = 15000`), prints "Your income is too low...".
3. **Indentation**:
    - The inner `if`/`else` is indented more (usually 4 spaces) to show it’s inside the outer `if`.

**Control Flow**:

- Imagine a flowchart:
    - First question: Is `age >= 18`?
        - Yes → Ask: Is `income >= 20000`?
            - Yes → Eligible for loan.
            - No → Income too low.
        - No → Too young.

---

### Example: Beach Day Decision

This example shows nested `if` statements deciding whether to go to the beach based on weather and humidity.

**Code**:

```python
weather = 'Sunny'
humidity = 35
if weather == 'Sunny':
    if humidity < 60:
        print('Let’s go to the beach! 🏖️')  # Output: Let’s go to the beach! 🏖️
    else:
        print('Hmmm, it’s a little humid for a beach day.')
else:
    print('It’s not sunny today... let’s try for another day.')
```

**How It Works**:

1. **Outer `if`**: Checks `weather == 'Sunny'`.
    - If `True` (e.g., `weather = 'Sunny'`), moves to inner `if`.
    - If `False` (e.g., `weather = 'Rainy'`), prints "It’s not sunny...".
2. **Inner `if`**: Checks `humidity < 60`.
    - If `True` (e.g., `humidity = 35`), prints "Let’s go to the beach!".
    - If `False` (e.g., `humidity = 65`), prints "Hmmm, it’s a little humid...".

**Alternative Scenario**:

- Change `humidity` to `65`:
    
    ```python
    humidity = 65
    # Output: Hmmm, it’s a little humid for a beach day.
    ```
    
- Change `weather` to `'Rainy'`:
    
    ```python
    weather = 'Rainy'
    # Output: It’s not sunny today... let’s try for another day.
    ```
    

---

### Additional Notes

- **Why Nest If Statements?**:
    - They let you handle multi-step decisions, like checking eligibility for a loan (age first, then income).
    - Common in real-world apps (e.g., if user is logged in, then check if they have permission).
- **Indentation Is Key**:
    - Python relies on indentation to know which code belongs to which `if`.
    - Example of wrong indentation:
        
        ```python
        if age >= 18:
        if income >= 20000:  # IndentationError
            print('Eligible')
        ```
        
    - Fix: Align inner `if` with 4 spaces under outer `if`.
- **Avoid Deep Nesting**:
    - Nesting more than 2–3 levels makes code hard to read.
    - Alternative: Combine conditions with `and`/`or`:
        
        ```python
        if age >= 18 and income >= 20000:
            print('You are eligible for a loan.')
        else:
            print('You are not eligible.')
        ```
        
    - This flattens the logic but may not always fit (e.g., different messages for age vs. income).
- **Improving the Beach Example**:
    - Add user input:
        
        ```python
        weather = input("Enter weather (Sunny/Rainy): ")
        humidity = float(input("Enter humidity (%): "))
        if weather == 'Sunny':
            if humidity < 60:
                print('Let’s go to the beach! 🏖️')
            else:
                print('Hmmm, it’s a little humid for a beach day.')
        else:
            print('It’s not sunny today... let’s try for another day.')
        ```
        
    - Add error handling:
        
        ```python
        try:
            weather = input("Enter weather (Sunny/Rainy): ")
            humidity = float(input("Enter humidity (%): "))
            if weather == 'Sunny':
                if 0 <= humidity <= 100:
                    if humidity < 60:
                        print('Let’s go to the beach! 🏖️')
                    else:
                        print('Hmmm, it’s a little humid for a beach day.')
                else:
                    print('Humidity must be between 0 and 100.')
            else:
                print('It’s not sunny today... let’s try for another day.')
        except ValueError:
            print('Please enter a valid number for humidity!')
        ```
        
- **Common Errors**:
    - **IndentationError**: Misaligned code blocks.
    - **NameError**: Using undefined variables (e.g., `Weather` instead of `weather`).
    - **TypeError**: Comparing wrong types (e.g., `humidity = '65'` without `float()`).
- **Control Flow Tip**:
    - Sketch a flowchart to visualize nested logic:
        - Outer `if`: Weather sunny? → Yes: Check humidity. → No: Skip to else.
        - Inner `if`: Humidity low? → Yes: Beach! → No: Too humid.

---

### Tips for Beginners

- Think of nested `if` statements as follow-up questions: "If it’s sunny, *then* is it dry enough?"
- Keep indentation clear—use 2 or 4 spaces consistently (most editors default to 4).
- Test all paths: Try `Sunny`/`35`, `Sunny`/`65`, `Rainy`/`35` to see each outcome.
- Avoid nesting too deep—combine conditions with `and` if possible.
- Use `print()` to debug: Add `print(weather, humidity)` to check values.
- Practice nesting in small programs to get comfortable with the flow.