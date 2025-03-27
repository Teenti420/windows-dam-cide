# # Windows Command Line & PowerShell - Practical Exercises 2

Files, Directories, Attributes & Permissions

## 1️ Directory Navigation & Management
1. Open **CMD** and navigate to `C:\Users\Public\`.
2. Create a new directory called `TrainingFiles`.
3. Inside `TrainingFiles`, create **3 subdirectories**: `Docs`, `Images`, `Scripts`.
4. List all the contents of `TrainingFiles`.

## 2️ File Creation & Modification
1. Inside `Docs`, create a text file called `notes.txt` and write `"Hello, Windows!"` in it.
2. Copy `notes.txt` to `BackupNotes.txt` in the same directory.
3. Move `BackupNotes.txt` to the `C:\Users\Public\Desktop\` directory.
4. Rename `notes.txt` to `project_notes.txt`.

## 3️ Managing Attributes
1. Check the current attributes of `project_notes.txt` using **CMD**.
2. Set `project_notes.txt` as **hidden and read-only**.
3. Remove the **read-only** attribute but keep it hidden.
4. Use **PowerShell** to check and modify the attributes again.

## 4️ Managing Permissions
1. Check the current permissions of the **Docs** folder using **CMD**.  
2. Remove **inheritance** so that files inside `Docs` no longer inherit its permissions.  
3. Grant **read-only** permission to a specific user (e.g., `User1`) for the file `project_notes.txt`.  
4. Verify the permissions of `project_notes.txt` for `User1`.  
5. Confirm that `User1` can **read** the file but cannot **modify** it.  
6. Restore **Full Control** permissions for `User1` on `project_notes.txt`. 
