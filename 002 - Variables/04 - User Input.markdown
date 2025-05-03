So far, we’ve only output data (like printing text). To make programs interactive, like websites or games, we need **input** from users. Python’s `input()` function lets us collect user input from the terminal.

### The `input()` Function

- The `input()` function prompts the user to type something and stores their response as a **string** (text).
- Syntax: `variable = input('Prompt message: ')`
- Example:
    
    ```python
    username = input('Enter your name: ')
    print(username)
    ```
    
- **How it works**:
    - The program displays "Enter your name: ".
    - The user types a name (e.g., "Alex") and presses Enter.
    - The input ("Alex") is stored in the `username` variable.
    - Printing `username` outputs "Alex".
- **Terminal flow**:
    
    ```
    Enter your name: Alex
    Alex
    ```
    

### Converting Input to Numbers

- By default, `input()` returns a string, even if the user types a number (e.g., "24" is text, not the number 24).
- To work with numbers, convert the input using `int()` for integers:
    
    ```python
    age = int(input('What is your age? '))
    print(age)
    ```
    
- **How it works**:
    - User sees "What is your age? " and types "24".
    - `int()` converts the string "24" to the integer `24`.
    - `age` stores `24`, which can be used in math operations.
- **Output**:
    
    ```
    What is your age? 24
    24
    ```
    

---

# Pythagorean Theorem Program

The **Pythagorean theorem** calculates the length of the hypotenuse (`c`) of a right triangle using the lengths of the two shorter sides (`a` and `b`):

**c = √(a² + b²)**

In Python, we use `**` for exponents and `** 0.5` for the square root.

### Task

Create a `hypotenuse.py` program that:

- Asks the user for two numbers (`a` and `b`).
- Calculates the hypotenuse (`c`).
- Prints the result.

### Steps and Code

1. **Get User Input**:
    - Prompt the user for `a` and `b`.
    - Convert inputs to integers (or floats for more precision).
2. **Calculate the Hypotenuse**:
    - Use the formula: `c = (a ** 2 + b ** 2) ** 0.5`.
3. **Write the Program**:
    
    ```python
    # hypotenuse.py
    a = float(input('Enter side a: '))
    b = float(input('Enter side b: '))
    c = (a ** 2 + b ** 2) ** 0.5
    print(f'The hypotenuse is {c:.2f}')
    ```
    
4. **Example Run**:
    - Input: `a = 3`, `b = 4`
    - Calculation: `c = √(3² + 4²) = √(9 + 16) = √25 = 5`
    - Output:
        
        ```
        Enter side a: 3
        Enter side b: 4
        The hypotenuse is 5.00
        ```
        

### Why Use `float()` Instead of `int()`?

- `float()` allows decimal inputs (e.g., 3.5), making the program more flexible.
- `int()` restricts inputs to whole numbers, which might not suit all triangles.

---

### Additional Notes

- **Square Root in Python**:
    - The square root of `x` is `x ** 0.5`.
    - Alternatively, use the `math` module for precision:
        
        ```python
        import math
        c = math.sqrt(a ** 2 + b ** 2)
        ```
        
- **Formatting Output**:
    - Use f-strings to make output clear:
        
        ```python
        print(f'The hypotenuse is {c:.2f}')  # Limits to 2 decimal places
        ```
        
    - Example: `5.00` instead of `5.0` or a long decimal.
- **Error Handling**:
    - If users enter non-numbers (e.g., "abc"), `float()` or `int()` will crash. For robustness:
        
        ```python
        try:
            a = float(input('Enter side a: '))
            b = float(input('Enter side b: '))
            c = (a ** 2 + b ** 2) ** 0.5
            print(f'The hypotenuse is {c:.2f}')
        except ValueError:
            print('Please enter valid numbers!')
        ```
        
- **Why Pythagorean Theorem?**:
    - It’s a practical math concept`=': It’s used in navigation, engineering, and video games to calculate distances.
    - Named after Pythagoras (circa 570 BC), a Greek philosopher.
- **Program Extensions**:
    - Validate inputs to ensure `a` and `b` are positive.
    - Add a loop to calculate multiple triangles:
        
        ```python
        while True:
            response = input('Calculate another? (yes/no): ')
            if response.lower() != 'yes':
                break
            a = float(input('Enter side a: '))
            b = float(input('Enter side b: '))
            c = (a ** 2 + b ** 2) ** 0.5
            print(f'The hypotenuse is {c:.2f}')
        ```
        
- **Bonus: Quadratic Formula**:
    - For a harder challenge, create a program to solve `ax² + bx + c = 0` using:
    **x = (-b ± √(b² - 4ac)) / (2a)**
    - Example:
        
        ```python
        import math
        a = float(input('Enter a: '))
        b = float(input('Enter b: '))
        c = float(input('Enter c: '))
        discriminant = b ** 2 - 4 * a * c
        if discriminant < 0:
            print('No real roots')
        else:
            x1 = (-b + math.sqrt(discriminant)) / (2 * a)
            x2 = (-b - math.sqrt(discriminant)) / (2 * a)
            print(f'Roots: x1 = {x1:.2f}, x2 = {x2:.2f}')
        ```
        

---

### Tips for Beginners

- Think of `input()` as a way to “ask” the user a question.
- Always convert inputs to numbers (`int` or `float`) for math operations.
- Test your program with known values (e.g., `a = 3`, `b = 4`, `c = 5`) to confirm it works.
- Use `float()` for inputs unless you’re sure only whole numbers are needed.
- Keep prompts clear, like "Enter side a: ", so users know what to type.
- Don’t worry if the math feels tricky—focus on getting the code to run first!