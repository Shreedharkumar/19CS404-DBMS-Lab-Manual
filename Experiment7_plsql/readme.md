# Experiment 7: PL/SQL – Variables, Control Structures and Loops
## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers
## Steps:
1. Declare two numeric variables and initialize them.
2. Use an IF statement to compare the values.
3. Display the greater number using DBMS_OUTPUT.PUT_LINE.
## Expected Output:
Greater number is: 80
## Code:
```
DECLARE
    num1 NUMBER := 80;  -- First number
    num2 NUMBER := 50;  -- Second number
BEGIN
    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;
```
## Output:
<img width="1789" height="299" alt="Screenshot 2025-11-03 153422" src="https://github.com/user-attachments/assets/94b375f5-f3d2-4f7d-befc-bf2ea3746b38" />

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Sum of first 10 natural numbers is: 55
## Code:
```
SET SERVEROUTPUT ON;

DECLARE
    n NUMBER := 10;       -- Number up to which sum is calculated
    i NUMBER := 1;        -- Loop counter
    total_sum NUMBER := 0; -- To store the sum
BEGIN
    WHILE i <= n LOOP
        total_sum := total_sum + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || total_sum);
END;
```
## Output:
<img width="1596" height="322" alt="Screenshot 2025-11-03 153442" src="https://github.com/user-attachments/assets/e417b6ae-5f52-4ef8-b170-556ad4359535" />


## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8
## Code:
```
SET SERVEROUTPUT ON;

DECLARE
    n NUMBER := 7;     -- Number of terms in the series
    a NUMBER := 0;     -- First term
    b NUMBER := 1;     -- Second term
    c NUMBER;          -- Next term
    i NUMBER := 3;     -- Counter starting from 3 since first two terms are already known
BEGIN
    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence:');
    DBMS_OUTPUT.PUT_LINE(a);
    DBMS_OUTPUT.PUT_LINE(b);

    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT_LINE(c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;
END;
```
## Output:
<img width="1836" height="475" alt="Screenshot 2025-11-03 153500" src="https://github.com/user-attachments/assets/43fc7c04-c0d8-4d9f-952f-524ff1698796" />


## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**Expected Output:**  
n = 1535  
Reversed number is 5351
## Code:
```
SET SERVEROUTPUT ON;

DECLARE
    n NUMBER := 1535;       -- Original number
    original NUMBER := 1535;-- To keep the original number for display
    reversed NUMBER := 0;   -- To store the reversed number
    digit NUMBER;           -- To extract each digit
BEGIN
    WHILE n > 0 LOOP
        digit := MOD(n, 10);              -- Get the last digit
        reversed := reversed * 10 + digit;-- Build the reversed number
        n := TRUNC(n / 10);               -- Remove the last digit
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('n = ' || original);
    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || reversed);
END;
```
## Output:
<img width="1659" height="369" alt="Screenshot 2025-11-03 153541" src="https://github.com/user-attachments/assets/b68150c8-0c39-4d9a-8f9e-d7b6bc03d4b2" />


## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15
## Code:
```
SET SERVEROUTPUT ON;

DECLARE
    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN
    IF a >= b AND a >= c THEN
        largest := a;
    ELSIF b >= a AND b >= c THEN
        largest := b;
    ELSE
        largest := c;
    END IF;

    DBMS_OUTPUT.PUT_LINE('a = ' || a || ', b = ' || b || ', c = ' || c);
    DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;
```
## Output:
<img width="1545" height="420" alt="Screenshot 2025-11-03 153559" src="https://github.com/user-attachments/assets/aac0301a-3486-482c-b9d3-821971e07197" />


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.

