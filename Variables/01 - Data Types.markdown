### Variables

Variables are containers for storing data values in programming. Each variable has a **name** and holds a **value**.

- **Variable Naming Rules**:
    - Can include letters (a-z, A-Z), numbers (0-9), and underscores (_).
    - Cannot start with a number.
    - Case-sensitive (e.g., `Name` ≠ `name`).
    - Examples of valid variable names and assignments:
        
        ```python
        name = 'Erlich Bachman'        # String
        user_id = 16180339887          # Integer
        progress = 0.75                # Float
        exp = 60                       # Integer
        verified = True                # Boolean
        ```
        
- **Assignment**:
    - The `=` sign assigns a value to a variable.
    - Variables can be reassigned new values:
        
        ```python
        xp = 70
        xp = 80
        print(xp)  # Output: 80
        ```
        

---

# Data Types

Data types define the kind of value a variable can hold. Below are the primary data types in Python:

### 1. Integer (int)

- Represents **whole numbers** (no decimal points).
- Includes zero, positive, and negative counting numbers.
- Use cases: Counting items (e.g., people, jellybeans).
- Examples:
    
    ```python
    year = 2023
    age = 32
    ```
    

### 2. Float (float)

- Represents **decimal numbers** (floating-point numbers).
- Used for fractions, precise measurements, or calculations requiring decimals.
- Use cases: Measurements (e.g., length, percentages, averages).
- Examples:
    
    ```python
    pi = 3.14159
    meal_cost = 12.99
    ```
    

### 3. String (str)

- Represents **text** or sequences of characters.
- Enclosed in single quotes (`'`) or double quotes (`"`).
- Use cases: Storing names, messages, usernames.
- Examples:
    
    ```python
    message = "good nite"
    username = '@snoopdogg'
    ```
    

### 4. Boolean (bool)

- Represents **logical values**: `True` or `False` (capitalized in Python).
- Used for conditions, comparisons, or flags.
- Named after George Boole, a mathematician who pioneered Boolean logic.
- Examples:
    
    ```python
    late_to_class = False
    cranky = True
    ```
    

---

### Additional Notes

- **Dynamic Typing in Python**:
    - Python is dynamically typed, meaning you don’t need to declare a variable’s type explicitly. The type is inferred from the assigned value.
    - Example:
        
        ```python
        x = 10      # x is an integer
        x = "hello" # x is now a string
        ```
        
- **Type Checking**:
    - Use the `type()` function to check a variable’s data type:
        
        ```python
        print(type(42))        # Output: <class 'int'>
        print(type(3.14))      # Output: <class 'float'>
        print(type("hello"))   # Output: <class 'str'>
        print(type(True))      # Output: <class 'bool'>
        ```
        
- **Common Operations by Data Type**:
    - **Integers/Floats**: Support arithmetic operations (`+`, , , `/`, etc.).
        
        ```python
        total = 10 + 5.5  # Output: 15.5 (float)
        ```
        
    - **Strings**: Support concatenation (`+`) and repetition ().
        
        ```python
        greeting = "Hello, " + "World!"  # Output: Hello, World!
        echo = "Hi! " * 3               # Output: Hi! Hi! Hi!
        ```
        
    - **Booleans**: Used in logical operations (`and`, `or`, `not`).
        
        ```python
        is_adult = age >= 18  # Output: True
        ```
        
- **Type Conversion**:
    - Convert between types using functions like `int()`, `float()`, `str()`, `bool()`:
        
        ```python
        num_str = "100"
        num_int = int(num_str)  # Converts string "100" to integer 100
        pi_int = int(3.14159)   # Converts float 3.14159 to integer 3
        ```
        
- **Why Data Types Matter**:
    - Different types support different operations (e.g., you can’t multiply strings by strings).
    - Choosing the right type ensures efficient memory usage and prevents errors.
    - Example error:
        
        ```python
        result = "5" + 3  # TypeError: can only concatenate str to str
        # Fix: Convert string to integer first
        result = int("5") + 3  # Output: 8
        ```
        

---

### Tips for Beginners

- Use **descriptive variable names** (e.g., `user_age` instead of `x`) for readability.
- Be mindful of data types when performing operations to avoid errors.
- Practice printing variables and checking their types to understand how Python handles data.

---
