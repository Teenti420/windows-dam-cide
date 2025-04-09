# PowerShell Scripting – Fundamentals & Exercises

## 🧠 PowerShell Scripting – Fundamentals

### 🔹 Declaring Variables
```powershell
$name = "Alice"
$age = 25
```
- PowerShell detects the type automatically.
- Variable names start with `$`.

---

### 🔹 Reading User Input
```powershell
$name = Read-Host "Enter your name"
Write-Host "Hello, $name!"
```

---

### 🔹 Arithmetic Operations
```powershell
$a = 5
$b = 3
$sum = $a + $b
$div = $a / $b
Write-Host "Sum: $sum, Division: $div"
```

---

### 🔹 Comparison Operators

| **Operator** | **Meaning**            | **Example**                  |
|--------------|------------------------|------------------------------|
| `-eq`        | Equal to               | `$a -eq $b`                  |
| `-ne`        | Not equal to           | `$a -ne $b`                  |
| `-gt`        | Greater than           | `$a -gt $b`                  |
| `-ge`        | Greater or equal       | `$a -ge $b`                  |
| `-lt`        | Less than              | `$a -lt $b`                  |
| `-le`        | Less or equal          | `$a -le $b`                  |
| `-like`      | Matches a pattern      | `$name -like "A*"`           |
| `-notlike`   | Doesn't match pattern  | `$name -notlike "B*"`        |
| `-match`     | Matches regex pattern  | `$text -match "[0-9]+"`      |
| `-contains`  | Item in collection     | `@(1,2,3) -contains 2`       |

---

### 🔹 If / Else Conditions
```powershell
if ($age -ge 18) {
    Write-Host "You're an adult"
} else {
    Write-Host "You're a minor"
}
```

---

### 🔹 Switch Statement
```powershell
switch ($day) {
    "Monday" { "Start of the week" }
    "Friday" { "Weekend incoming!" }
    default { "Just another day." }
}
```

---

### 🔹 While Loop
```powershell
$i = 1
while ($i -le 5) {
    Write-Host "Number: $i"
    $i++
}
```

---

### 🔹 For Loop
```powershell
for ($i = 1; $i -le 5; $i++) {
    Write-Host "Looping: $i"
}
```

---

### 🔹 Foreach Loop
```powershell
$names = @("Ana", "Luis", "Carlos")
foreach ($name in $names) {
    Write-Host "Hello, $name!"
}
```
