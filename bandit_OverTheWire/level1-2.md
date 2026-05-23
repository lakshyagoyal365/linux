## Bandit level 1→2
Go to website https://overthewire.org/wargames/bandit for hint of each level.

## 🎯 Challenge
The goal is to find the password for the next level which is stored in a file called `-` located in the home directory
We are given:
- Host: `bandit.labs.overthewire.org`
- Port: `2220`
- Username: `bandit1`
- Password: `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If__laksh`

In the previous level we retrieved the password for [bandit1](level0-1.md)
## 📝 Steps

1. **Open your terminal**  
   On your Linux machine, launch the terminal application.

2. **Run the SSH command**  
   Type the following command and press **Enter**:
   ```bash
   ssh bandit1@bandit.labs.overthewire.org -p 2220
   ```
  
<details>

  - `ssh` : Secure Shell, used to connect to remote servers
  - `bandit1@...`  : Username and host
  - `-p 2220`  : specifies the custom port 2220(default uses port 22)
</details>

![Diagram of process](assets/2_1.png)

3. **Enter password**
   ```bash 
   ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If__laksh 
   ```
(Note: The password will remain hidden as you type — this is normal.)

3. **Retrieve password for Level1**

- Once logged in, list files
```bash
ls
 ```
![Diagram of process](assets/2_2.png)

- Read the file **readme**
```bash
cat readme
```
![Diagram of process](assets/2_3.png)
You can copy the password
- Exit the session
```bash
exit 
   ```
![Diagram of process](assets/1_3.png)

<details>

- `ls` : list directory contents

  `ls -a` : don't ignore files starting with . (it is used to list hidden files)


- `cat filename` : read and display the contents of file
- `exit` : closes current shell session
</details>

4. **Save the password on local system**

Saving password to the file **pswd.txt**
   ```bash
   echo "263JGJPfgU6LtdEvgfWU1XP5yac29mFx__laksh">>pswd.txt
   ```
  
![Diagram of process](assets/2_4.png)

<details>

- `mkdir` : make directory
- `cd` : change directory
- `echo` : prints text or variable to the terminal

You can combine `echo` with redirection operators (> or >>) to save text into files

`echo "smth">filename` : Creates file if don't exist or overwrites the existing file with given text
`echo "smth">>filename` : Appends text to the end of a file without deleting what’s already inside.
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
#### 💬 Need help? [Text me on WhatsApp ➡️](https://wa.me/918619372532?text=Hello)
