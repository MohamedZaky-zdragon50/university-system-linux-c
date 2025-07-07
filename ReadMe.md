 🎓 University System - Linux C Project
	
A terminal-based, **role-based access control system** written in **C**, designed to simulate Linux-like permission management in a university setting. It distinguishes between three roles: **Dean**, **Professors**, and **Students**, each with granular and realistic privileges for interacting with the file system using real Linux commands through `system()` calls.

---

 📂 Project Directory Structure

```
/university
├── /dean         # Accessible only by the Dean
├── /professors   # Read/Write by professors, Read-only for students
└── /students     # Isolated student directories for personal access
```

---

🛡️ Role-Based Access Control (RBAC)

### 🧑‍💼 Dean

  Full administrative control
  List/view files and directories
  Copy, move, delete files/directories across roles
  Modify permissions via `chmod`
  Create symbolic (soft/hard) links
  Define persistent aliases (via `.bashrc`)
  Perform advanced file searches (`find`, `grep`)

### 👨‍🏫 Professors

 Manage teaching material in `/professors`
 Create/delete directories
 Copy/move files within allowed scope
 Redirect outputs to logs or assignments
 Define aliases for repetitive commands
 View/search files in `/professors`

### 👩‍🎓 Students

 List and manage personal files in `/students`
 Create/update assignments using redirection (`>`, `>>`)
 Copy/move files within their directory
 Create personal aliases
 Search and view file contents using `cat`, `head`, `tail`, `grep`

---

## ⚙️ Functional Highlights

 Dynamic, role-specific menu interface
 File & directory listing using `ls`
 Permission handling through `chmod`
 Full file system interaction: `mkdir`, `rm`, `cp`, `mv`, `touch`
 Linking: `ln` (hard) and `ln -s` (soft)
 Shell redirection for writing/appending data to files
 Persistent aliases added to `.bashrc`
 File content viewing tools (`cat`, `head`, `tail`)
 Powerful search support via `find` and `grep`

---

## 🚀 Getting Started

### 📋 Prerequisites

* 🐧 Linux OS (Ubuntu preferred)
* 🧰 GCC Compiler
* 👥 Three Linux users created: `dean`, `professors`, `students`

### ⚙️ Compile the Program

```bash
gcc university_system.c -o university_system
```

### ▶️ Run the Program

```bash
sudo ./university_system
```

> ⚠️ `sudo` is required to allow user switching (`su`) inside the program.

---

## 🧪 Sample Console Output

```
Login As:
> 1: Dean
> 2: Professors
> 3: Students
> 99: Exit

Choose Operation:
> 1: List files
> 2: Change permissions
> 3: Create/Delete files
...
```
---

## 👨‍💻 Author

**Mohamed Zaky**
🎓 Student, Faculty of Computers and Artificial Intelligence – Helwan University
📧 Email: zakym6883@gmail.com

---

## 🔮 Future Enhancements

* 🖥️ Build a TUI (Text-based UI) using `ncurses`
* 📑 Implement structured logging for audit trails
* 🔗 Connect real Linux user groups with granular access
* ✅ Add automated test suites for file/permission validation

---

## 📝 Notes & Best Practices

* Ensure home directories exist for each user with correct permissions:

```bash
sudo mkdir -p /home/{dean,professors,students}
sudo chown dean:dean /home/dean
sudo chown professors:professors /home/professors
sudo chown students:students /home/students
```

* Best run in a controlled virtual environment or VM.
* Educational purpose only — do not use in production without sandboxing.
