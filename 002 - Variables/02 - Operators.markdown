Operators are symbols that perform operations on variables and values. Python’s arithmetic operators enable mathematical calculations, making it easy to manipulate data stored in variables.

### Arithmetic Operators

Python supports the following arithmetic operators:

- `+` **Addition**: Adds two values.
- **Subtraction**: Subtracts one value from another.
- **Multiplication**: Multiplies two values.
- `/` **Division**: Divides one value by another (returns a float).
- `%` **Modulo**: Returns the remainder of division.

**Example Usage**:

```python
score = 0           # Initialize score to 0
score = 4 + 3       # score = 7
score = 4 - 3       # score = 1
score = 4 * 3       # score = 12
score = 4 / 3       # score ≈ 1.3333
score = 4 % 3       # score = 1 (remainder of 4 ÷ 3)
print(score)        # Output: 1
```

### Operator Precedence

- **Parentheses `()`** have the highest precedence, ensuring expressions inside them are evaluated first.
- Example: `(2 + 3) * 4` evaluates to `20` (not `14`), as `2 + 3` is calculated first.

### Practical Example: Calculating a Tip

Arithmetic operators can combine variables and numbers for real-world calculations, like computing a 20% tip:

```python
pizza = 2.99
coke = 0.99
total = pizza + coke        # total = 3.98
tip = total * 0.2           # tip = 0.796
print(tip)                  # Output: 0.796
```

Or, using parentheses for a single-line calculation:

```python
tip = (pizza + coke) * 0.2  # Same result: 0.796
```

---

### Temperature Conversion Program

The task is to create a Python program (`temperature.py`) that converts the current temperature in Brooklyn, NY, from Fahrenheit (°F) to Celsius (°C) using the formula:

**Celsius = (Fahrenheit - 32) / 1.8**

### Steps and Code

1. **Find the Current Temperature**:
    - As of April 12, 2025, the current temperature in Brooklyn, NY, is approximately 39.2°F (based on available weather data).
    - Note: Real-time weather data should ideally be checked, but this value is used for the example.
2. **Write the Program**:
    
    ```python
    # temperature.py
    fahrenheit = 39.2
    celsius = (fahrenheit - 32) / 1.8
    print(celsius)  # Output: ≈ 4.0
    ```
    
3. **Explanation**:
    - Assign the Fahrenheit temperature to a variable (`fahrenheit = 39.2`).
    - Apply the formula: Subtract 32, then divide by 1.8.
    - Print the result, which is approximately 4.0°C.

### Verification

- Using the formula: `(39.2 - 32) / 1.8 = 7.2 / 1.8 = 4.0°C`.
- This matches expected results for a cool April day in Brooklyn.

---

### Additional Notes

- **Division (`/`)**:
    - Always returns a float in Python (e.g., `4 / 2 = 2.0`, not `2`).
    - For integer division, use `//` (e.g., `4 // 3 = 1`).
- **Modulo (`%`)**:
    - Useful for finding remainders, like checking if a number is even (`num % 2 == 0`).
    - Example: `7 % 3 = 1` (since 7 ÷ 3 leaves a remainder of 1).
- **Floating-Point Precision**:
    - Calculations like `4 / 3` may produce long decimals (e.g., `1.3333333333333333`).
    - To round output, use `round()`:
        
        ```python
        result = 4 / 3
        print(round(result, 2))  # Output: 1.33
        ```
        
- **Order of Operations (PEMDAS)**:
    - **P**arentheses, **E**xponents, **M**ultiplication/**D**ivision (left to right), **A**ddition/**S**ubtraction (left to right).
    - Example: `2 + 3 * 4 = 14` (not `20`), as multiplication precedes addition.
- **Alternative Formula Insight**:
    - The Celsius conversion formula can also be written as `C = (F - 32) * 5 / 9`, since `5 / 9 ≈ 0.5556` is the inverse of `1.8`.
    - Both produce the same result, but `(F - 32) / 1.8` is simpler for coding.
- **Real-World Application**:
    - Temperature conversions are common in weather apps, scientific calculations, and international travel.
    - Ensure input validation in real programs (e.g., check if `fahrenheit` is a number).
- **Extending the Program**:
    - To make it interactive:
        
        ```python
        fahrenheit = float(input("Enter temperature in °F: "))
        celsius = (fahrenheit - 32) / 1.8
        print(f"{fahrenheit}°F is {celsius:.1f}°C")
        ```
        
    - This accepts user input and formats output (e.g., `39.2°F is 4.0°C`).

---

### Tips for Beginners

- Use **descriptive variable names** (e.g., `fahrenheit` instead of `x`) for clarity.
- Test calculations with known values to verify formulas (e.g., 32°F = 0°C, 212°F = 100°C).
- Break complex calculations into steps for debugging:
    
    ```python
    fahrenheit = 39.2
    temp_diff = fahrenheit - 32
    celsius = temp_diff / 1.8
    ```
    
- Practice combining operators in small programs to build confidence.