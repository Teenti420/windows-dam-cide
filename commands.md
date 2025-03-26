# Windows Command Line and PowerShell Commands

## General Commands

If you want to know more information about a command, you just have to use the atribute **/?** after the name of the comand on CMD. If you use cmdlets, you have to use its version, Get-Help CmdletName

### `help`
- **CMD:** Displays a list of available commands.
  ```cmd
  help
  ```
- **PowerShell:** Equivalent is `Get-Help`.
  ```powershell
  Get-Help
  ```

### `cls`
- **CMD:** Clears the screen.
  ```cmd
  cls
  ```
- **PowerShell:** Equivalent is `Clear-Host`.
  ```powershell
  Clear-Host
  ```

### `color`
- **CMD:** Changes the console text and background color.
  ```cmd
  color 0A
  ```
  - `0A`: Black background, Green text.
- **PowerShell:** Equivalent is `Write-Host` with color options.
  ```powershell
  Write-Host "Hello" -ForegroundColor Green
  ```

### `date`
- **CMD:** Displays or sets the system date.
  ```cmd
  date
  ```
- **PowerShell:** Equivalent is `Get-Date`.
  ```powershell
  Get-Date
  ```

### `exit`
- **CMD:** Closes the command prompt.
  ```cmd
  exit
  ```
- **PowerShell:** Same command.
  ```powershell
  exit
  ```

### `shutdown`
- **CMD:** Used to shutdown or restart the computer.
  ```cmd
  shutdown /s   # Shutdown the computer
  shutdown /p   # Shutdown without waiting
  shutdown /r /t 30   # Restart in 30 seconds
  shutdown /l   # Logout user
  ```
- **PowerShell:**
  ```powershell
  Stop-Computer   # Shutdown
  Restart-Computer   # Restart
  ```

### `time`
- **CMD:** Displays or sets the system time.
  ```cmd
  time
  ```
- **PowerShell:**
  ```powershell
  Get-Date -Format "HH:mm:ss"
  ```

### `title`
- **CMD:** Sets the title of the command prompt window.
  ```cmd
  title My Command Window
  ```
- **PowerShell:**
  ```powershell
  $host.ui.RawUI.WindowTitle = "My PowerShell Window"
  ```

### `ver`
- **CMD:** Displays the Windows version.
  ```cmd
  ver
  ```
- **PowerShell:**
  ```powershell
  $PSVersionTable.OS
  ```

### `vol`
- **CMD:** Displays the disk volume label and serial number.
  ```cmd
  vol C:
  ```
- **PowerShell:**
  ```powershell
  Get-Volume -DriveLetter C
  ```

### `label`
- **CMD:** Creates, changes, or deletes a volume label.
  ```cmd
  label C: MyDrive
  ```
- **PowerShell:**
  ```powershell
  Set-Volume -DriveLetter C -NewFileSystemLabel "MyDrive"
  ```

## File and Directory Management

### `path`
- **CMD:** Displays or sets a search path for executable files.
  ```cmd
  path
  ```
- **PowerShell:**
  ```powershell
  $env:Path
  ```

### `attrib`
- **CMD:** Changes file attributes.
  ```cmd
  attrib +r myfile.txt  # Set read-only
  attrib -h myfile.txt  # Remove hidden attribute
  ```
- **PowerShell:**
  ```powershell
  (Get-Item myfile.txt).IsReadOnly = $true
  ```

### `cd` / `chdir`
- **CMD:** Changes the current directory.
  ```cmd
  cd C:\Users
  ```
- **PowerShell:**
  ```powershell
  Set-Location C:\Users
  ```

### `type`
- **CMD:** Displays the contents of a file.
  ```cmd
  type C:\Users\file.txt
  ```
- **PowerShell:**
  ```powershell
  Get-Content C:\Users\file.txt
  ``` 

### `copy`
- **CMD:** Copies files from one location to another.
  ```cmd
  copy file1.txt C:\Backup
  ```
- **PowerShell:**
  ```powershell
  Copy-Item file1.txt -Destination C:\Backup
  ```

### `del` / `erase`
- **CMD:** Deletes files.
  ```cmd
  del file1.txt
  ```
- **PowerShell:**
  ```powershell
  Remove-Item file1.txt
  ```

### `dir`
- **CMD:** Lists directory contents.
  ```cmd
  dir C:\
  ```
- **PowerShell:**
  ```powershell
  Get-ChildItem C:\
  ```

### `md` / `mkdir`
- **CMD:** Creates a new directory.
  ```cmd
  mkdir NewFolder
  ```
- **PowerShell:**
  ```powershell
  New-Item -Path "NewFolder" -ItemType Directory
  ```

### `move`
- **CMD:** Moves files or directories.
  ```cmd
  move file.txt C:\NewLocation
  ```
- **PowerShell:**
  ```powershell
  Move-Item file.txt -Destination C:\NewLocation
  ```

### `rd` / `rmdir`
- **CMD:** Removes a directory.
  ```cmd
  rmdir EmptyFolder
  ```
- **PowerShell:**
  ```powershell
  Remove-Item EmptyFolder -Recurse
  ```

### `ren` / `rename`
- **CMD:** Renames a file or folder.
  ```cmd
  ren oldname.txt newname.txt
  ```
- **PowerShell:**
  ```powershell
  Rename-Item oldname.txt -NewName newname.txt
  ```

### `sort`
- **CMD:** Sorts input text.
  ```cmd
  sort < unsorted.txt > sorted.txt
  ```
- **PowerShell:**
  ```powershell
  Get-Content unsorted.txt | Sort-Object | Set-Content sorted.txt
  ```

### `tree`
- **CMD:** Displays a graphical directory structure.
  ```cmd
  tree C:\
  ```
- **PowerShell:**
  ```powershell
  Get-ChildItem C:\ -Recurse
  ```

### `xcopy`
- **CMD:** Copies files and directories, including subdirectories.
  ```cmd
  xcopy C:\Source C:\Destination /E
  ```
- **PowerShell:**
  ```powershell
  Copy-Item -Path C:\Source -Destination C:\Destination -Recurse

## Wildcards in Windows

Special characters used to represent one or more characters in a string of text.

- **`*`**: Represents any number of characters and in any quantity.  
  **Example:**
  - **CMD/PowerShell:**  
    ```cmd
    dir *.txt
    ```

- **`?`**: Represents a single character in the specified position.  
  **Example:**
  - **CMD/PowerShell:**  
    ```cmd
    dir filename?.txt
    ```

- **`[]`**: Represents a set of characters within the specified range.  
  **Example:**
  - **CMD/PowerShell:**  
    ```cmd
    dir filename[1-3].jpg
    ```

- **`!`**: Represents the negation of the value that precedes it.  
  **Example:**
  - **CMD/PowerShell:**  
    ```cmd
    dir filename[!1-3].jpg
    ```

- **`~`**: Disables the execution of a wildcard, meaning it searches literally for the specified character.  
  **Example:**
  - **CMD/PowerShell:**  
    ```cmd
    dir ~*.txt
    ```