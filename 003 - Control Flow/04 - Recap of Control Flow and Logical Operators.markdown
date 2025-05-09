This lesson recaps **control flow** and builds a fun quiz inspired by the **Sorting Hat** from *Harry Potter*. The Sorting Hat assigns Hogwarts students to one of four houses: **Gryffindor**, **Ravenclaw**, **Hufflepuff**, or **Slytherin**, based on their answers to questions.

### Recap of Key Concepts

- **Control Flow**: Determines the order in which code runs.
    - **if statement**: Runs code if a condition is `True`.
    - **elif clause**: Checks additional conditions if previous ones are `False`.
    - **else clause**: Runs if no conditions are `True`.
- **Relational Operators**: Compare values:
    - `==` (equal), `!=` (not equal), `>` (greater), `<` (less), `>=`, `<=`.
- **Logical Operators**: Combine conditions:
    - `and` (both true), `or` (at least one true), `not` (reverses truth).

**Example**:

```python
review = 4.2
if review >= 4.5:
    print('Extraordinary')
elif review >= 4:
    print('Excellent')  # Output: Excellent
elif review >= 3:
    print('Good')
else:
    print('Eh')
```

- Checks conditions in order; stops at the first `True`.

---

# Sorting Hat Program

**Task**:
Create a program that asks the user three questions, assigns points to Hogwarts houses based on their answers, and prints each house’s score. Optionally, find the house with the most points.

**Program Requirements**:

- Use `int()` and `input()` to get numeric answers.
- Track points for **Gryffindor**, **Ravenclaw**, **Hufflepuff**, and **Slytherin**.
- Handle invalid inputs with "Wrong input."
- Questions and scoring:
    
    **Q1. Do you like Dawn or Dusk?**
    
    1. Dawn: Gryffindor +1, Ravenclaw +1
    2. Dusk: Hufflepuff +1, Slytherin +1
    3. Else: "Wrong input."
    
    **Q2. When I’m dead, I want people to remember me as:**
    
    1. The Good: Hufflepuff +2
    2. The Great: Slytherin +2
    3. The Wise: Ravenclaw +2
    4. The Bold: Gryffindor +2
    5. Else: "Wrong input."
    
    **Q3. Which kind of instrument most pleases your ear?**
    
    1. The violin: Slytherin +4
    2. The trumpet: Hufflepuff +4
    3. The piano: Ravenclaw +4
    4. The drum: Gryffindor +4
    5. Else: "Wrong input."
- Print each house’s score.
- **Bonus**: Identify the house with the highest score.

**Code**:

```python
gryffindor = 0
ravenclaw = 0
hufflepuff = 0
slytherin = 0

# Question 1
answer1 = int(input("Do you like Dawn or Dusk?\\n1) Dawn\\n2) Dusk\\n"))
if answer1 == 1:
    gryffindor += 1
    ravenclaw += 1
elif answer1 == 2:
    hufflepuff += 1
    slytherin += 1
else:
    print("Wrong input.")

# Question 2
answer2 = int(input("When I’m dead, I want people to remember me as:\\n1) The Good\\n2) The Great\\n3) The Wise\\n4) The Bold\\n"))
if answer2 == 1:
    hufflepuff += 2
elif answer2 == 2:
    slytherin += 2
elif answer2 == 3:
    ravenclaw += 2
elif answer2 == 4:
    gryffindor += 2
else:
    print("Wrong input.")

# Question 3
answer3 = int(input("Which kind of instrument most pleases your ear?\\n1) The violin\\n2) The trumpet\\n3) The piano\\n4) The drum\\n"))
if answer3 == 1:
    slytherin += 4
elif answer3 == 2:
    hufflepuff += 4
elif answer3 == 3:
    ravenclaw += 4
elif answer3 == 4:
    gryffindor += 4
else:
    print("Wrong input.")

# Print scores
print(f"Gryffindor: {gryffindor}")
print(f"Ravenclaw: {ravenclaw}")
print(f"Hufflepuff: {hufflepuff}")
print(f"Slytherin: {slytherin}")
```

**How It Works**:

1. Initialize house scores to `0`.
2. For each question:
    - Use `input()` to prompt the user and `int()` to convert the answer to a number.
    - Use `if`/`elif`/`else` to update scores based on the answer.
    - Print "Wrong input." for invalid answers (e.g., `0`, `5`).
3. Add points as specified (e.g., Dawn gives Gryffindor and Ravenclaw +1 each).
4. Print final scores for all houses.

**Example Run**:

```
Do you like Dawn or Dusk?
1) Dawn
2) Dusk
1
When I’m dead, I want people to remember me as:
1) The Good
2) The Great
3) The Wise
4) The Bold
3
Which kind of instrument most pleases your ear?
1) The violin
2) The trumpet
3) The piano
4) The drum
3
Gryffindor: 1
Ravenclaw: 7
Hufflepuff: 0
Slytherin: 0
```

- **Explanation**:
    - Q1: Dawn (1) → Gryffindor +1, Ravenclaw +1
    - Q2: The Wise (3) → Ravenclaw +2
    - Q3: The piano (3) → Ravenclaw +4
    - Total: Gryffindor = 1, Ravenclaw = 1 + 2 + 4 = 7, Hufflepuff = 0, Slytherin = 0

---

### Bonus: Finding the Winning House

To print the house with the most points, compare scores and handle ties or zero cases.

**Bonus Code Addition**:

```python
# After printing scores
max_score = max(gryffindor, ravenclaw, hufflepuff, slytherin)
if max_score == 0:
    print("No house has points yet!")
else:
    print("House with the most points:")
    if gryffindor == max_score:
        print("🦁 Gryffindor")
    if ravenclaw == max_score:
        print("🦅 Ravenclaw")
    if hufflepuff == max_score:
        print("🦡 Hufflepuff")
    if slytherin == max_score:
        print("🐍 Slytherin")
```

**How It Works**:

- `max()` finds the highest score.
- Checks if `max_score` is 0 (no points earned).
- Prints all houses with the highest score to handle ties (e.g., if Gryffindor and Ravenclaw both have 5).

**Example Output** (added to above run):

```
Gryffindor: 1
Ravenclaw: 7
Hufflepuff: 0
Slytherin: 0
House with the most points:
🦅 Ravenclaw
```

---

### Additional Notes

- **Why This Program?**:
    - Combines `if`/`elif`/`else`, relational operators (`==`), and user input to create an interactive quiz.
    - Mimics real-world scenarios like surveys or personality tests.
- **Error Handling**:
    - `int(input())` crashes if the user enters non-numbers (e.g., "abc"). Add a `try` block:
        
        ```python
        try:
            answer1 = int(input("Do you like Dawn or Dusk?\\n1) Dawn\\n2) Dusk\\n"))
            if answer1 == 1:
                gryffindor += 1
                ravenclaw += 1
            elif answer1 == 2:
                hufflepuff += 1
                slytherin += 1
            else:
                print("Wrong input.")
        except ValueError:
            print("Please enter a number!")
        ```
        
    - Repeat for other questions.
- **Improving the Program**:
    - Use a loop to retry invalid inputs:
        
        ```python
        while True:
            try:
                answer1 = int(input("Do you like Dawn or Dusk?\\n1) Dawn\\n2) Dusk\\n"))
                if answer1 in [1, 2]:
                    break
                print("Wrong input.")
            except ValueError:
                print("Please enter a number!")
        if answer1 == 1:
            gryffindor += 1
            ravenclaw += 1
        else:
            hufflepuff += 1
            slytherin += 1
        ```
        
    - Add question repetition or a welcome message:
        
        ```python
        print("Welcome to the Sorting Hat Quiz!")
        ```
        
- **Common Errors**:
    - **ValueError**: Non-numeric input (fix with `try`/`except`).
    - **SyntaxError**: Missing colons or indentation in `if` blocks.
    - **Logic Error**: Wrong points (e.g., `+= 2` instead of `+= 1`)—double-check rules.
- **Relational Operators in Use**:
    - `answer1 == 1` checks exact equality.
    - Use `in` for cleaner checks: `if answer2 in [1, 2, 3, 4]`.
- **Bonus Challenge Insight**:
    - Finding the max score requires comparing all houses.
    - Ties need multiple prints (e.g., two houses with 5 points).
    - Use a dictionary for cleaner code (advanced):
        
        ```python
        houses = {"Gryffindor": gryffindor, "Ravenclaw": ravenclaw, "Hufflepuff": hufflepuff, "Slytherin": slytherin}
        max_score = max(houses.values())
        winners = [house for house, score in houses.items() if score == max_score]
        print("House(s) with the most points:", ", ".join(winners))
        ```
        

---

### Tips for Beginners

- Break the program into small parts: write one question, test it, then add the next.
- Test with valid inputs (1, 2) and invalid ones (0, "abc") to see how the program reacts.
- Use `print(gryffindor)` after each question to debug point changes.
- Think of `if`/`elif` as a flowchart: "If this, do that; otherwise, check the next."
- For the bonus, compare scores manually first before using `max()`.
- Have fun role-playing as the Sorting Hat—try different answers to get each house!