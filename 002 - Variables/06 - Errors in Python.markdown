Errors (or "bugs") are mistakes in code that prevent it from running correctly. The term "bug" became famous in 1947 when a moth caused a computer malfunction, but it may date back to Thomas Edison in 1878. Errors are normal in programming—what makes a great coder is learning to **find and fix them**!

Python provides error messages to help identify issues. Let’s explore three common errors: **SyntaxError**, **NameError**, and **TypeError**.

# 1. SyntaxError

- **What is it?**: Happens when Python can’t understand your code due to incorrect syntax (like a typo, missing punctuation, or wrong keywords).
- **Common causes**:
    - Missing parentheses `)`, colons `:`, or quotes `'`/`"`.
    - Misspelled keywords (e.g., `pritn` instead of `print`).
- **Example**:
    
    ```python
    print(Hello, World!
    # SyntaxError: invalid syntax
    ```
    
    - **Problem**: Missing closing parenthesis `)` and quotes around `Hello, World!`.
    - **Fix**:
        
        ```python
        print("Hello, World!")  # Output: Hello, World!
        ```
        
- **Error Message**:
    
    ```
    File "main.py", line 1
      print(Hello, World!
                        ^
    SyntaxError: invalid syntax
    ```
    
    - **File "[main.py](http://main.py/)", line 1**: Shows the file and line number.
    - **^**: Points to where Python detected the issue (but the real error might be earlier).
- **Tip**: Check for missing or extra symbols near the arrow.

# 2. NameError

- **What is it?**: Happens when you use a variable that hasn’t been defined or is misspelled.
- **Common causes**:
    - Forgetting to create a variable.
    - Typo in variable name (e.g., `greeting` vs. `greetings`).
- **Example**:
    
    ```python
    print(greetings)
    # NameError: name 'greetings' is not defined
    ```
    
    - **Problem**: `greetings` was never defined.
    - **Fix**:
        
        ```python
        greetings = 'Howdy 🤠'
        print(greetings)  # Output: Howdy 🤠
        ```
        
- **Tip**: Check variable names for typos and ensure they’re defined before use.

# 3. TypeError

- **What is it?**: Occurs when you perform an operation on incompatible data types.
- **Common causes**:
    - Mixing strings with numbers without conversion.
    - Using a function on the wrong type.
- **Example**:
    
    ```python
    message = 'The air quality is '
    print(message + 28)
    # TypeError: can only concatenate str (not "int") to str
    ```
    
    - **Problem**: You can’t add a string and an integer.
    - **Fix**:
        
        ```python
        message = 'The air quality is '
        print(message + str(28))  # Output: The air quality is 28
        ```
        
    - Converts `28` to a string using `str()`.
- **Tip**: Use `str()`, `int()`, or `float()` to convert types when needed.

---

# Bug Catcher Exercise

The following program has errors. Your job is to find and fix them:

```python
butterflies = 10
beetles = 12
ladybugs = 20

print('I caught ' + butterflies + ' 🦋 butterflies!')
print('I caught ' + beetles + ' 🪲 beetles!')
print('I caught ' + ladybug + ' 🐞 ladybugs!)

print('I caught ' + str(total) + ' total bugs!'
```

### Errors and Fixes

1. **TypeError in print statements**:
    - Lines like `print('I caught ' + butterflies + ' 🦋 butterflies!')` try to concatenate a string with an integer (`butterflies`).
    - **Fix**: Convert numbers to strings with `str()`:
        
        ```python
        print('I caught ' + str(butterflies) + ' 🦋 butterflies!')
        print('I caught ' + str(beetles) + ' 🪲 beetles!')
        ```
        
2. **NameError in ladybugs line**:
    - `ladybug` is used, but the variable is named `ladybugs` (plural).
    - **Fix**: Correct the variable name:
        
        ```python
        print('I caught ' + str(ladybugs) + ' 🐞 ladybugs!')
        ```
        
3. **SyntaxError in ladybugs line**:
    - Missing closing quotation mark `'` after `ladybugs!`.
    - **Fix**: Add the missing `'`.
4. **NameError in total line**:
    - `total` is used but never defined.
    - **Fix**: Calculate `total` before printing:
        
        ```python
        total = butterflies + beetles + ladybugs
        ```
        
5. **TypeError in total line**:
    - Even with `str(total)`, ensure it’s concatenated correctly.
    - **Fix**: Already addressed by defining `total`.

### Corrected Program

```python
butterflies = 10
beetles = 12
ladybugs = 20

print('I caught ' + str(butterflies) + ' 🦋 butterflies!')
print('I caught ' + str(beetles) + ' 🪲 beetles!')
print('I caught ' + str(ladybugs) + ' 🐞 ladybugs!')

total = butterflies + beetles + ladybugs
print('I caught ' + str(total) + ' total bugs!')
```

### Output

```
I caught 10 🦋 butterflies!
I caught 12 🪲 beetles!
I caught 20 🐞 ladybugs!
I caught 42 total bugs!
```

### Alternative Using f-Strings

For cleaner code, use f-strings:

```python
butterflies = 10
beetles = 12
ladybugs = 20

print(f'I caught {butterflies} 🦋 butterflies!')
print(f'I caught {beetles} 🪲 beetles!')
print(f'I caught {ladybugs} 🐞 ladybugs!')

total = butterflies + beetles + ladybugs
print(f'I caught {total} total bugs!')
```

---

# Additional Notes

- **Why Errors Happen**:
    - **SyntaxError**: Like forgetting a comma in a sentence.
    - **NameError**: Like calling someone by the wrong name.
    - **TypeError**: Like trying to add apples and oranges without a plan.
- **Reading Error Messages**:
    - **File and line number**: Tells you where to look.
    - **Error type**: Hints at the problem (e.g., `SyntaxError` = bad code structure).
    - **Description**: Explains what went wrong (e.g., "not defined" = missing variable).
    - **^**: Points to the issue, but check nearby code too.
- **Debugging Tips**:
    - **Start at the top**: Fix the first error in the message, as later errors may disappear.
    - **Comment out code**: Use `#` to disable lines and isolate the problem:
        
        ```python
        # print('I caught ' + butterflies + ' 🦋 butterflies!')  # Test without this line
        ```
        
    - **Print variables**: Check values with `print(butterflies)` to ensure they’re correct.
    - **Google it**: Search the error message (e.g., "Python TypeError can only concatenate str") for solutions.
    - **Test small changes**: Fix one thing, run the code, and repeat.
- **Preventing Errors**:
    - Double-check variable names for consistency.
    - Convert types (`str()`, `int()`) when mixing data.
    - Test code with simple inputs first (e.g., `butterflies = 1`).
- **Beyond These Errors**:
    - Other errors like `ZeroDivisionError` (e.g., `10 / 0`) or `IndexError` (accessing a list beyond its length) may appear.
    - Check Python’s official documentation or search online for unfamiliar errors.

---

### Tips for Beginners

- **Don’t panic**: Errors are clues, not failures.
- **Read slowly**: Error messages point you to the problem—focus on the first one.
- **Fix one at a time**: Solving the top error often clears others.
- **Test often**: Run your code after small changes to catch issues early.
- **Learn by breaking**: Experiment with wrong code to see what errors appear.
- **Have fun debugging**: Think of it as solving a puzzle!