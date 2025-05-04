# 💸 Converting South American Currencies to USD 💸

Welcome to the **Currency** challenge, a fantastic way to practice **variables**, **input()**, and basic math in Python! This beginner-friendly problem lets you create a currency converter for Colombian pesos, Peruvian soles, and Brazilian reais to US dollars (USD). You’ll use real-world exchange rates and combine everything you’ve learned about data types, arithmetic, and user input. In this note, we’ll break down the problem, explain the requirements, and provide a step-by-step solution. Let’s make some money magic! 💰

---

## 🎯 Problem Explanation

### What is the Problem?

The task is to create a Python program called `currency.py` that:

1. Asks the user for the amounts they have in **Colombian pesos (COP)**, **Peruvian soles (PEN)**, and **Brazilian reais (BRL)** using `input()`.
2. Converts each amount to **US dollars (USD)** using current exchange rates.
3. Calculates the **total** in USD and prints it.

The output should match this format exactly:

```
What do you have left in pesos? 5600
What do you have left in soles? 105
What do you have left in reais? 280
413.0
```

- The user inputs amounts for each currency.
- The program uses exchange rates to convert to USD.
- The final output is the total USD, as a float (e.g., `413.0`).

### Key Requirements:

- **Program**: Create `currency.py`.
- **Input**:
    - Use `input()` to ask for amounts in pesos, soles, and reais.
    - Convert inputs to numbers (using `int()` or `float()`) for calculations.
- **Exchange Rates**:
    - Research current rates for COP, PEN, and BRL to USD.
    - Rates change daily, so we’ll use approximate mid-market rates for April 17, 2025.
- **Calculation**:
    - Convert each currency to USD: `amount * exchange_rate`.
    - Sum the USD values to get the total.
- **Output**:
    - Match the example format: three prompts, user inputs, and the total USD.
    - The total should be a float (e.g., `413.0`).

### Example Output:

```
What do you have left in pesos? 5600
What do you have left in soles? 105
What do you have left in reais? 280
413.0
```

### Why Use Variables and Input?

- **Variables**: Store user inputs and exchange rates for easy calculations.
- **Input()**: Gets user data (currency amounts) dynamically.
- **Arithmetic**: Uses multiplication () and addition (`+`) to convert and sum amounts.
- **Data Types**: Converts string inputs to numbers (`int` or `float`) for math.

---

## 🕵️‍♂️ Problem Breakdown

Let’s dissect the problem into its core components:

1. **User Input**:
    - Ask three questions:
        - “What do you have left in pesos?”
        - “What do you have left in soles?”
        - “What do you have left in reais?”
    - Store each answer in a variable (e.g., `pesos`, `soles`, `reais`).
    - Convert inputs to numbers using `float()` (since exchange rates and totals may involve decimals).
2. **Exchange Rates**:
    - Find current exchange rates for:
        - COP to USD (Colombian pesos).
        - PEN to USD (Peruvian soles).
        - BRL to USD (Brazilian reais).
    - Rates as of April 17, 2025 (approximated from web sources):
        - 1 COP ≈ 0.00024 USD (1 USD ≈ 4166.67 COP).
        - 1 PEN ≈ 0.266 USD (1 USD ≈ 3.759 PEN).
        - 1 BRL ≈ 0.175 USD (1 USD ≈ 5.714 BRL).
    - These are mid-market rates; actual rates may vary slightly.
3. **Conversion**:
    - For each currency, calculate USD:
        - `pesos_usd = pesos * cop_to_usd`
        - `soles_usd = soles * pen_to_usd`
        - `reais_usd = reais * brl_to_usd`
    - Sum them: `total_usd = pesos_usd + soles_usd + reais_usd`.
4. **Output**:
    - Print the total USD as a float (e.g., `413.0`).
    - Ensure the input prompts match the example exactly.

### Challenges to Consider:

- **Exchange Rates**: Rates fluctuate, so we need reliable, recent values.
- **Input Validation**: The problem assumes valid numeric inputs, but we could add error handling.
- **Precision**: Using `float` ensures decimal accuracy, but we need to match the output format (`413.0`).
- **Exact Formatting**: The prompts and output must follow the example, with no extra text.

---

## 🛠️ Step-by-Step Solution

Let’s build the `currency.py` program step-by-step, using the example inputs and exchange rates.

### Step 1: Add a Comment

Start with a comment to describe the program:

```python
# Currency converter for COP, PEN, BRL to USD
```

- `#` makes this a comment, ignored in the output.
- Explains the program’s purpose.

### Step 2: Get User Inputs

Use `input()` to ask for the amounts in each currency and convert to `float`:

```python
pesos = float(input("What do you have left in pesos? "))
soles = float(input("What do you have left in soles? "))
reais = float(input("What do you have left in reais? "))
```

- Each `input()` matches the example prompts exactly.
- `float()` converts the string input to a number for calculations.
- Stored in variables `pesos`, `soles`, `reais` (e.g., `5600`, `105`, `280`).

### Step 3: Define Exchange Rates

Set the exchange rates based on approximate mid-market rates for April 17, 2025:

```python
cop_to_usd = 0.00024  # 1 COP = 0.00024 USD
pen_to_usd = 0.266    # 1 PEN = 0.266 USD
brl_to_usd = 0.175    # 1 BRL = 0.175 USD
```

- Rates sourced from web data (rounded for simplicity).
- Use floats for precision, as rates often have decimals.

### Step 4: Convert to USD

Calculate the USD value for each currency:

```python
pesos_usd = pesos * cop_to_usd
soles_usd = soles * pen_to_usd
reais_usd = reais * brl_to_usd
```

- `pesos * cop_to_usd`: Converts pesos to USD (e.g., `5600 * 0.00024 = 1.344`).
- `soles * pen_to_usd`: Converts soles to USD (e.g., `105 * 0.266 = 27.93`).
- `reais * brl_to_usd`: Converts reais to USD (e.g., `280 * 0.175 = 49.0`).

### Step 5: Calculate Total USD

Sum the USD amounts:

```python
total_usd = pesos_usd + soles_usd + reais_usd
```

- Adds the converted amounts (e.g., `1.344 + 27.93 + 49.0 = 78.274`).
- Stored as a float for decimal precision.

### Step 6: Print the Total

Output the total USD:

```python
print(total_usd)
```

- Prints the sum (e.g., `78.274`).
- The example shows `413.0`, so we’ll verify with the example inputs.

### Complete Program:

Combine all parts into `currency.py`:

```python
# Currency converter for COP, PEN, BRL to USD
pesos = float(input("What do you have left in pesos? "))
soles = float(input("What do you have left in soles? "))
reais = float(input("What do you have left in reais? "))

cop_to_usd = 0.00024  # 1 COP = 0.00024 USD
pen_to_usd = 0.266    # 1 PEN = 0.266 USD
brl_to_usd = 0.175    # 1 BRL = 0.175 USD

pesos_usd = pesos * cop_to_usd
soles_usd = soles * pen_to_usd
reais_usd = reais * brl_to_usd

total_usd = pesos_usd + soles_usd + reais_usd

print(total_usd)
```

---

## 🧪 Testing the Solution

Let’s test with the example inputs to ensure the output matches:

**Inputs**:

- Pesos: `5600`
- Soles: `105`
- Reais: `280`

**Calculations**:

- Pesos to USD: `5600 * 0.00024 = 1.344`
- Soles to USD: `105 * 0.266 = 27.93`
- Reais to USD: `280 * 0.175 = 49.0`
- Total: `1.344 + 27.93 + 49.0 = 78.274`

**Output**:

```
What do you have left in pesos? 5600
What do you have left in soles? 105
What do you have left in reais? 280
78.274
```

**Note**: The example output shows `413.0`, which suggests different exchange rates were used in the example. Let’s try to match the example by adjusting rates to reverse-engineer the result:

- Total USD = `413.0` for `5600 COP`, `105 PEN`, `280 BRL`.
- Assume:
    - `5600 * cop_to_usd + 105 * pen_to_usd + 280 * brl_to_usd = 413.0`.
- Using approximate rates from the example era (e.g., 2021 rates from XE.com):
    - 1 COP ≈ 0.00026 USD (1 USD ≈ 3846 COP).
    - 1 PEN ≈ 0.27 USD (1 USD ≈ 3.704 PEN).
    - 1 BRL ≈ 0.19 USD (1 USD ≈ 5.263 BRL).
- Recalculate:
    - `5600 * 0.00026 = 1.456`
    - `105 * 0.27 = 28.35`
    - `280 * 0.19 = 53.2`
    - Total: `1.456 + 28.35 + 53.2 = 83.006` (still not 413.0).

The example’s `413.0` likely uses outdated or simplified rates. For accuracy, we’ll stick with the 2025 rates but note the discrepancy. To match the example exactly, we could use:

```python
cop_to_usd = 0.002   # Adjusted to get closer to example
pen_to_usd = 2.5     # Adjusted
brl_to_usd = 1.0     # Adjusted
```

**Recalculate with Adjusted Rates**:

- `5600 * 0.002 = 11.2`
- `105 * 2.5 = 262.5`
- `280 * 1.0 = 280.0`
- Total: `11.2 + 262.5 + 280.0 = 553.7` (closer but not exact).

Since the example’s rates don’t align with real-world data, we’ll use the 2025 rates for correctness and note the example’s output may reflect a specific context.

**Test with Different Inputs**:

- Pesos: `10000`, Soles: `50`, Reais: `100`
- `10000 * 0.00024 = 2.4`
- `50 * 0.266 = 13.3`
- `100 * 0.175 = 17.5`
- Total: `2.4 + 13.3 + 17.5 = 33.2`

**Output**:

```
What do you have left in pesos? 10000
What do you have left in soles? 50
What do you have left in reais? 100
33.2
```

---

## 🌟 Why This Solution Works

- **Meets Requirements**:
    - Creates `currency.py` with three `input()` prompts.
    - Converts COP, PEN, BRL to USD using exchange rates.
    - Outputs the total USD as a float.
- **Beginner-Friendly**:
    - Uses simple variables, `input()`, and arithmetic.
    - No complex logic, perfect for early learners.
- **Accurate**:
    - Uses recent exchange rates from reliable sources.
    - Handles decimal precision with `float`.
- **Matches Format**:
    - Prompts match the example exactly.
    - Output is a single number, as required.

---

## 🧠 Tips for Solving Similar Problems

1. **Research Exchange Rates**:
    - Check sites like XE.com or Wise.com for current rates.
    - Note that rates change daily, so use the latest available.
2. **Use Float for Money**:
    - Convert inputs to `float()` for decimal accuracy.
    - Example: `float(input(...))` instead of `int()`.
3. **Match the Example**:
    - Copy the prompt text exactly (e.g., “What do you have left in pesos?”).
    - Ensure the output format (e.g., `413.0`) aligns with expectations.
4. **Test Calculations**:
    - Use a calculator to verify conversions (e.g., `5600 * 0.00024`).
    - Check the total matches the sum of individual conversions.
5. **Keep It Simple**:
    - Stick to basic arithmetic and `print()` for beginner-level code.
    - Avoid loops or complex error handling unless required.

---

## 🚀 Level Up Your Solution

Want to make your converter even cooler? Try these ideas:

- **Add a Welcome Message**:
    
    ```python
    print("Welcome to the South America Currency Converter! 💸")
    pesos = float(input("What do you have left in pesos? "))
    ```
    
- **Show Individual Conversions**:
    
    ```python
    # Currency converter for COP, PEN, BRL to USD
    pesos = float(input("What do you have left in pesos? "))
    soles = float(input("What do you have left in soles? "))
    reais = float(input("What do you have left in reais? "))
    
    cop_to_usd = 0.00024
    pen_to_usd = 0.266
    brl_to_usd = 0.175
    
    pesos_usd = pesos * cop_to_usd
    soles_usd = soles * pen_to_usd
    reais_usd = reais * brl_to_usd
    
    total_usd = pesos_usd + soles_usd + reais_usd
    
    print(f"Pesos to USD: ${pesos_usd}")
    print(f"Soles to USD: ${soles_usd}")
    print(f"Reais to USD: ${reais_usd}")
    print(total_usd)
    ```
    
    **Output** (for 5600, 105, 280):
    
    ```
    What do you have left in pesos? 5600
    What do you have left in soles? 105
    What do you have left in reais? 280
    Pesos to USD: $1.344
    Soles to USD: $27.93
    Reais to USD: $49.0
    78.274
    ```
    
- **Input Validation**:
    
    ```python
    # Currency converter for COP, PEN, BRL to USD
    try:
        pesos = float(input("What do you have left in pesos? "))
        soles = float(input("What do you have left in soles? "))
        reais = float(input("What do you have left in reais? "))
    except ValueError:
        print("Please enter valid numbers!")
        exit()
    
    cop_to_usd = 0.00024
    pen_to_usd = 0.266
    brl_to_usd = 0.175
    
    pesos_usd = pesos * cop_to_usd
    soles_usd = soles * pen_to_usd
    reais_usd = reais * brl_to_usd
    
    total_usd = pesos_usd + soles_usd + reais_usd
    
    print(total_usd)
    ```
    
- **Round the Output**:
    
    ```python
    print(round(total_usd, 2))  # Prints 78.27 instead of 78.274
    ```
    

---

## 🛑 Common Pitfalls and How to Avoid Them

1. **Incorrect Exchange Rates**:
    - **Problem**: Using outdated or wrong rates.
    - **Fix**: Check reliable sources like XE.com or Wise.com.
2. **String Inputs**:
    - **Problem**: Forgetting to convert `input()` to `float`.
    - **Fix**: Use `float(input(...))` for calculations.
3. **Wrong Prompt Text**:
    - **Problem**: Prompts don’t match the example (e.g., “Enter pesos”).
    - **Fix**: Copy the exact text: “What do you have left in pesos?”.
4. **Output Mismatch**:
    - **Problem**: Printing extra text or wrong format.
    - **Fix**: Print only the total (e.g., `78.274`), no labels like “Total:”.
5. **Invalid Inputs**:
    - **Problem**: Non-numeric inputs (e.g., “abc”) cause errors.
    - **Fix**: The problem assumes valid inputs, but add `try-except` for robustness.

---

## 🎉 Final Thoughts

The **Currency** challenge is an exciting way to practice **variables**, **input()**, and arithmetic in Python while exploring real-world currency conversion! By turning Colombian pesos, Peruvian soles, and Brazilian reais into USD, you’re combining coding skills with practical math. This beginner-friendly project is like being a financial wizard, calculating totals with just a few lines of code. Keep experimenting with `print()`, variables, and inputs, and soon you’ll be ready for more Python adventures. Cha-ching—you’re on your way to coding greatness! 💸

Happy coding! 🌈