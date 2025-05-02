Exponents represent repeated multiplication, like 2³ (2 × 2 × 2 = 8). In Python, since typing superscripts (e.g., ², ³) isn’t practical, we use the `**` operator to calculate exponents.

### The `*` Operator

- The `*` operator raises a number (base) to a power (exponent).
- Syntax: `base ** exponent`
- Examples:
    
    ```python
    score = 2 ** 2  # 2² = 4
    score = 2 ** 3  # 2³ = 8
    score = 2 ** 4  # 2⁴ = 16
    score = 2 ** 5  # 2⁵ = 32
    print(score)    # Output: 32
    ```
    

### Key Points

- Exponentiation is like multiplication but faster for repeated values (e.g., 2 ** 3 = 2 × 2 × 2).
- Works with integers, floats, or even negative exponents:
    
    ```python
    print(3.5 ** 2)   # Output: 12.25
    print(2 ** -1)    # Output: 0.5 (1/2)
    ```
    

---

### BMI Calculation Program

The **Body Mass Index (BMI)** is a simple formula used to estimate body fat based on weight and height. It’s calculated as:

**BMI = weight (kg) / (height (m))²**

### Task

Create a Python program (`bmi.py`) to calculate your own BMI.

### Steps and Code

1. **Gather Your Data**:
    - Weight in kilograms (e.g., 70 kg).
    - Height in meters (e.g., 1.75 m).
    - Note: If you know your height in centimeters (e.g., 175 cm), convert to meters by dividing by 100 (175 ÷ 100 = 1.75 m).
2. **Write the Program**:
    
    ```python
    # bmi.py
    weight = 70        # Your weight in kilograms
    height = 1.75      # Your height in meters
    bmi = weight / (height ** 2)  # BMI formula
    print(bmi)         # Output: ≈ 22.86
    ```
    
3. **How It Works**:
    - `height ** 2` squares the height (e.g., 1.75² = 3.0625).
    - Divide weight by the squared height (e.g., 70 ÷ 3.0625 ≈ 22.86).
    - The result is your BMI, typically rounded to two decimals for clarity.

### Example Calculation

- For weight = 70 kg, height = 1.75 m:
    - height² = 1.75 × 1.75 = 3.0625
    - BMI = 70 ÷ 3.0625 ≈ 22.86
- A BMI of 22.86 falls in the "normal" range (18.5–24.9), but ranges vary by context.

---

### Additional Notes

- **Why Exponents Matter**:
    - Exponents are used in formulas like BMI, area calculations (e.g., circle area = πr²), or scientific computations.
    - The `*` operator is efficient and clear for these tasks.
- **Order of Operations**:
    - Exponentiation (`*`) has higher precedence than multiplication, division, addition, or subtraction.
    - Use parentheses to control order:
        
        ```python
        result = (2 + 3) ** 2  # (5)² = 25
        result = 2 + 3 ** 2    # 2 + 9 = 11
        ```
        
- **Common Pitfalls**:
    - Ensure height is in **meters**, not centimeters, to avoid errors (e.g., 175 cm = 1.75 m).
    - Dividing by zero (e.g., `height = 0`) causes an error, so validate inputs in real programs.
- **Improving the Program**:
    - Add user input for flexibility:
        
        ```python
        weight = float(input("Enter weight in kg: "))
        height = float(input("Enter height in meters: "))
        bmi = weight / (height ** 2)
        print(f"Your BMI is {bmi:.2f}")
        ```
        
    - This formats the output (e.g., "Your BMI is 22.86") and handles decimals.
- **About BMI**:
    - BMI is a rough estimate of body fat, developed in the 1850s by a mathematician, not a health expert.
    - It doesn’t account for muscle mass, age, or other factors, so use it as a general guide, not a definitive health measure.
- **Rounding for Clarity**:
    - BMI results often have many decimals. Use `round()` for cleaner output:
        
        ```python
        bmi = 22.857142857142858
        print(round(bmi, 2))  # Output: 22.86
        ```
        

---

### Tips for Beginners

- Think of `*` as “to the power of” to make exponents intuitive.
- Test your BMI program with different weights and heights to see how results change.
- Double-check units (kg for weight, meters for height) before calculating.
- Experiment with exponents in other formulas, like calculating the area of a square (`side ** 2`).
- Don’t worry if BMI seems oversimplified—it’s just a starting point for learning Python math!