## Bandit level 5→6
Go to website https://overthewire.org/wargames/bandit for hint of each level.


## 🎯 Challenge
The goal is to find the password for the next level which is stored in a file somewhere under the inhere directory and has all of the following properties:
- human-readable
- 1033 bytes in size
- not executable

We are given:

- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit5`
- Password: `(use the one from Level 4→5)`

In the previous level, we retrieved the password that lets us log in as [bandit5](level4-5.md)

## 📝 Steps

1. **Open your terminal**

On your Linux machine, launch the terminal application.

2. **Run the SSH command**

Type the following command and press **Enter**:
   ```bash
   ssh bandit5@bandit.labs.overthewire.org -p 2220
   ```

<details>

- `ssh` : Secure Shell, used to connect to remote servers
- `bandit5@...`  : Username and host
- `-p 2220`  : specifies the custom port 2220(default uses port 22)
</details>

![Diagram of process](assets/6_1.png)

3. **Enter password**
   ```bash 
   4oQYVPkxZ00EOO5pTW81FB8j8lxXGUQw__laksh 
   ```
(Note: The password will remain hidden as you type — this is normal.)

⚠️ **Disclaimer**: Password is intentionally altered. Use the actual one you retrieved in the previous level.

4. **Retrieve password for Level6**

- We used `file` command to find only **human-readable**, which **not-executable** and has size **1033 bytes** file out of so many files in **inhere**.

```bash
find inhere -type f -size 1033c ! -executable -exec file {} \; | grep "ASCII text"
```
<details>

- `find`  : used to search for files and directories. It can look inside folders and apply filters (like type, name, size).
- `find inhere` : it tells `find` to look inside the folder **inhere**
- `-type f` : Restricts the search to files only (not directories).

  command works fine even without it
  ![Diagram](assets/6_1extra.png)

- `-size` : This flag filters the result by size.

    `1033c` : `c` = "bytes"(character count)
- `! -executable` : exclude executable files.

    `!` : **NOT**
    `-executable` : files you can run as program(chmod +x).
- `-exec` : This flag lets you run another command on each file that **find** discovers.
  Sample use-case :
  ![Diagram](assets/5_2extra.png)
- `file` : tells you the type of content inside a file.
- `{}` : it is a placeholder, the name of files from **find inhere** are placed inside it.
- `\;` : marks the end of the -exec command.
- `2>/dev/null` : This part hides the error.
  Works fine without this but is a good practice
  ![Diagram](assets/5_3extra.png)

- `|`**(pipe)** : Takes the output of one command and sends it as input to another.

  Here, the results of `file` are sent into `grep`.
- `grep` : searches for lines containing a specific word or phrase.
</details>



![Diagram of process](assets/6_2.png)

### ⚡ Quick Tips
- Use `ls -lh` to check file sizes and permissions.

- Run `file <filename>` to confirm it’s a text file before cat.

---
- Read the file `-file07`
```bash
cat inhere/maybehere07/.file2
```

![Diagram of process](assets/6_3.png)

You can copy the password


- **Exit the session**
```bash
exit 
   ```
![Diagram of process](assets/1_3.png)

---
### 📜All used commands
<details>

- `ssh username@host` : Secure Shell, used to connect to remote servers
- `ls` : list directory contents
- `find`  : used to search for files and directories. It can look inside folders and apply filters (like type, name, size).
- `file`  : tells you the type of content inside a file (e.g., text, binary, image).
- `grep`  : searches for lines containing a specific word or phrase.
- `cat <filename>` : read and display the contents of file
- `exit` : closes current shell session
</details>

---
✨ Pro tip: You can always refer to the manual pages for deeper understanding.
Just type:
```bash
man <command>
```
for example :
```bash
man ls
```

---
#### 💬 Need help?
- [ExplainShell](https://explainshell.com): Paste any command (like `ls -lh`) and it breaks down each flag and argument.
- Reading resource :  [Linux Command Line and Shell Scripting Bible](https://github.com/linuxqueenn12/popular-Hacking-books-/blob/833e3e07dea7c463137ac6b689e1eba3236a5029/Linux%20Command%20Line%20and%20Shell%20Scripting%20Bible%203rd%20Edition%20%7BPRG%7D.pdf)

[Text me on WhatsApp ➡️](https://wa.me/918619372532?text=Hello)