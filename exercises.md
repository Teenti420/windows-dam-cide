# Windows Command Line & PowerShell - Practical Exercises

## 🎯 Basic Level

### 1️⃣ Open CMD and PowerShell
- Open **Command Prompt** (`cmd`) and **PowerShell** from the Start menu.
- Check the version of each using the appropriate command.

### 2️⃣ Clear the screen
- Use the command to clear the screen in **CMD**.
- Do the same in **PowerShell**.

### 3️⃣ Check system information
- Display the **Windows version** in **CMD**.
- Display the **OS name and architecture** in **PowerShell**.

### 4️⃣ Change the console title
- Change the **CMD** window title to `Windows Admin`.
- Do the same in **PowerShell**.

### 5️⃣ Display the current date and time
- Show the system **date** in **CMD**.
- Show only the **time** in **PowerShell**.

---

## 🔧 Intermediate Level

### 6️⃣ Navigate through directories
- Move to the `C:\Windows` folder using **CMD**.
- Return to the **user’s home directory**.
- Repeat the same using **PowerShell**.

### 7️⃣ Create and delete directories
- Create a folder named `TestFolder` in `C:\Users\Public` using **CMD**.
- Delete it using **PowerShell**.

### 8️⃣ File operations
- Create a text file named `testfile.txt` in `C:\Users\Public` using **CMD**.
- Write `"Hello, CMD!"` inside it using **CMD**.
- Copy the file to `C:\Users\Public\Backup` using **PowerShell**.

### 9️⃣ Modify file attributes
- Mark the file as **hidden** using **CMD**.
- Remove the hidden attribute using **PowerShell**.

### 🔟 Sorting and filtering data
- Display a **sorted list** of files in `C:\Windows` (by size) using **PowerShell**.

---

## 🚀 Advanced Level

### 1️⃣1️⃣ Shutdown and restart automation
- Schedule the computer to **shut down in 60 seconds** using **CMD**.
- Cancel the shutdown before it happens.
- Restart the computer immediately using **PowerShell**.

### 1️⃣2️⃣ Scripting in PowerShell
- Create a PowerShell script (`system_info.ps1`) that:
  - Displays the **system name**.
  - Lists all **running processes**.
  - Saves this information in `C:\Users\Public\system_report.txt`.

### 1️⃣3️⃣ Using environment variables
- Display the **PATH environment variable** using **CMD**.
- Add a new temporary folder (`C:\CustomPath`) to `PATH` using **PowerShell**.

### 1️⃣4️⃣ Recursive file operations
- Use **xcopy** in **CMD** to copy all contents of `C:\Users\Public\Documents` to `C:\Backup` including subfolders.
- Delete all `.txt` files from `C:\Backup` using **PowerShell**.

### 1️⃣5️⃣ Tree structure visualization
- Display the **directory structure** of `C:\Users` in **CMD**.
- Save the output to a file called `directory_tree.txt`.

---

## 📌 Additional Challenge: Batch and PowerShell Automation
- **Create a batch file (`cleanup.bat`) that:**
  - Clears **temporary files** (`C:\Windows\Temp`).
  - Deletes all files in `C:\Users\Public\Downloads`.
- **Create a PowerShell script (`cleanup.ps1`) that does the same but also:**
  - Lists the total **size of deleted files** before proceeding.

---

## 📊 Expected Learning Outcomes
✅ Understanding of **basic and advanced commands** in CMD and PowerShell.  
✅ Ability to **navigate, create, modify, and delete files and directories**.  
✅ Understanding of **automation and scripting** for administration tasks.  
✅ Awareness of **system commands and security implications**.  

---

🔹 **Want to add more exercises or need clarifications? Feel free to contribute!** 🚀
