# Windows File System, Directories, Attributes & Permissions – Theory

## 📝 File System Basics  
Windows uses the **NTFS** (New Technology File System), which supports:  
- File and directory permissions.  
- Compression and encryption.  
- Large file support.  

Common paths:  
- `C:\Users\` → User profiles.  
- `C:\Program Files\` → Installed applications.  
- `C:\Windows\` → System files.  

## 📁 File and Directory Commands  
| **Action**       | **CMD Command** | **PowerShell Cmdlet** |
|-----------------|----------------|-----------------------|
| List contents  | `dir` | `Get-ChildItem` (`ls` alias) |
| Change directory | `cd folder` | `Set-Location folder` (`cd` alias) |
| Create directory | `mkdir folder` | `New-Item -Path folder -ItemType Directory` |
| Delete directory | `rmdir folder` | `Remove-Item folder -Recurse` |
| Create file | `echo "Hello" > file.txt` | `New-Item file.txt -ItemType File` |
| Copy file | `copy file.txt newfile.txt` | `Copy-Item file.txt newfile.txt` |
| Move file | `move file.txt C:\Temp\` | `Move-Item file.txt C:\Temp\` |
| Delete file | `del file.txt` | `Remove-Item file.txt` |

## 🔖 File Attributes in Windows  
Files and directories in Windows have attributes that define their behavior:
- **Read-Only (`R`)** – Prevents modification.
- **Hidden (`H`)** – Hides the file from default view.
- **System (`S`)** – Marks as a system file.
- **Archive (`A`)** – Used for backup operations.

### 🔹 CMD: Managing Attributes
- View attributes of a file:
  ```cmd
  attrib file.txt
  ```
- Set file as hidden and read-only:
  ```cmd
  attrib +H +R file.txt
  ```
- Remove attributes:
  ```cmd
  attrib -H -R file.txt
  ```

### 🔹 PowerShell: Managing Attributes
- View attributes:
  ```powershell
  (Get-Item file.txt).Attributes
  ```
- Set file as hidden:
  ```powershell
  (Get-Item file.txt).Attributes += 'Hidden'
  ```
- Remove hidden attribute:
  ```powershell   
  (Get-Item file.txt -Force).Attributes -= 'Hidden'
  ```

## 🔐 File Permissions in Windows (NTFS)  
Windows controls file access using **Access Control Lists (ACLs)**.  
Permissions include:  
- **Read** (`R`) – Open/view file contents.  
- **Write** (`W`) – Modify file contents.  
- **Execute** (`X`) – Run a file (only for executables).  
- **Full Control** – All permissions.  

### 🔹 CMD: Managing Permissions
- View permissions:  
  ```cmd
  icacls file.txt
  ```
- Grant read/write to a user:  
  ```cmd
  icacls file.txt /grant UserName:(R,W)
  ```
- Remove a permission:  
  ```cmd
  icacls file.txt /remove UserName
  ```

OPTIONS:

- /grant - Assign permissions
- /deny - Deny permissions
- /remove - Remove permissions
- /inheritance - Inheritance configuration
      :r to delete
      :e to enable
- /save and /restore - export and import permissions

MODIFICATIONS:

- OI (Object Inherit) - Permissions apply to files in the folder
- CI (Container Inherit) - Permissions apply to subfolders.
- IO (Inherit Only) - Permissions do not apply to the current folder, only to its children (files and folders)
- NP (No Propagate Inherit): Permissions are not inherited beyond immediate children

PERMISSIONS:

- F (Full Control): Total control over the resource
- M (Modify): Allows you to modify the content, but not to change permissions or properties
- RX (Read and Execute): Allows reading and executing
- R (Read): Allow read only
- W (Write): Allows writing

### 🔹 PowerShell: Managing Permissions
- View permissions:  
  ```powershell
  Get-Acl file.txt
  ```
- Grant Full Control to a user:  
  ```powershell
  $acl = Get-Acl file.txt
  $rule = New-Object System.Security.AccessControl.FileSystemAccessRule("UserName","FullControl","Allow")
  $acl.SetAccessRule($rule)
  Set-Acl file.txt $acl
  ```