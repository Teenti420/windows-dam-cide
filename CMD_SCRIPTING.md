# Windows Command Line & PowerShell - Scripting Exercises

## 📜 Windows Scripting - CMD & PowerShell

### 1️⃣ Introduction to Windows Scripting
- **Batch Scripts (`.bat`)**: Scripts executed in CMD, used for task automation.

---

## 📌 CMD (Batch) Script Basics

### 🔹 Script 1: Print and Pause
Save this code as `hello.bat` and execute it:
```batch
@echo off
echo Hello, welcome to scripting!
pause
```
📌 **Explanation**:
- `@echo off` → Hides command execution.
- `echo` → Displays text on the screen.
- `pause` → Waits for user input.

---

### 🔹 Script 2: Create a Directory and File
```batch
@echo off
mkdir C:\Users\Public\ScriptsTest
cd C:\Users\Public\ScriptsTest
echo This is a test file > testfile.txt
echo Folder and file created successfully!
pause
```
📌 **Explanation**:
- `mkdir` → Creates a directory.
- `cd` → Changes the directory.
- `echo > filename.txt` → Creates a file and writes inside it.

---

### 🔹 Script 3: Loop and User Input
```batch
@echo off
set /p name=Enter your name:
echo Hello, %name%!
pause
```
📌 **Explanation**:
- `set /p variable=` → Takes user input.
- `set /a variable=` → Defines a variable
- `%variable%` → Uses the stored value.

---

### 🔹 Script 4: Conditional Statement (IF)
```batch
@echo off
set /p age=Enter your age:
if %age% GEQ 18 (
    echo You are an adult.
) else (
    echo You are a minor.
)
pause
```
📌 **Explanation**:
- `if` → Evaluates conditions.
- `GEQ` → Greater than or equal to.

Comparison operators should be used with `IF`. Use `/I` for case-insensitive string comparisons.

| **Operator**  | **Description** | **Example** |
|--------------|----------------|-------------|
| `==` | Equal to | `if %var1% == %var2% echo They are equal` |
| `NEQ` | Not equal to | `if %var1% NEQ %var2% echo They are different` |
| `LSS` | Less than | `if %var1% LSS 10 echo It is less than 10` |
| `LEQ` | Less than or equal to | `if %var1% LEQ 10 echo It is less than or equal to 10` |
| `GTR` | Greater than | `if %var1% GTR 10 echo It is greater than 10` |
| `GEQ` | Greater than or equal to | `if %var1% GEQ 10 echo It is greater than or equal to 10` |

---

### 🔹 Script 5: Loop Example
```batch
@echo off
set /a count=1
:loop
echo Count: %count%
set /a count=%count%+1
if %count% LEQ 5 goto loop
echo Loop completed!
pause
```
📌 **Explanation**:
- `:label` and `goto` → Creates loops.
- `LEQ` → Less than or equal to.

---
