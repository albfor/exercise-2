# Exercise 2

## Walkthrough

1. Make a dir, **exercise-2**, and open it in vscode.
```
mkdir exercise-2 && code exercise-2
```
2. Open the terminal of vscode and create a repository and run **git status** and **git log**
```
git init
```
```
git status
```
```
git log
```
3. Create **README.md** and write **# Exercise 2**
```
echo "# Exercise 2" > README.md
```
4. Create **.gitignore** and ignore all **.txt** files.
```
echo "*.txt" > .gitignore
```
5. Add changes to the staging area
```
git add .
```
6. Make a commit with the message "Init commit"
```
git commit -m "Init commit"
```
7. Run **git status**, **git log** and **git log --oneline**.
```
git status
```
```
git log
```
```
git log --oneline
```
8. Remove **README.md** using **git rm**
```
git rm README.md
```
9. Run ** git status** and then unstage the change using **git restore**
```
git status
```
```
git restore --staged README.md
```
10. Run **git status** and **discard** the changes using **git restore**
```
git status
```
```
git restore README.md
```
11. Instead of all **.txt** files, ignore all files without **.c, .md** or **.sh** extensions.

Open your .gitignore file with a text editor and change the content to 

> \*
>
> !\*.c
>
> !\*.sh
>
> !\*.md

12. Run **git status** and add **.gitignore** 
```
git status && git add .gitignore
```
13. Create two files, **main.c** and **run.sh**
```
touch main.c run.sh
```
14. Write the below code with printf to run.sh

clear && gcc main.c -o main && ./main
```
printf "clear && gcc main.c -o main && ./main" > run.sh
```
15. Write the below code with printf to main.c

#include <stdio.h>\n\nint main(void) \n{\n\treturn 0;\n}
```
printf "#include <stdio.h>\n\nint main(void) \n{\n\treturn 0;\n}" > main.c
```
16. Run **git status** and add changes to staging area.
```
git status
```
```
git add .
```
17. **Commit** changes with the message "**First commit**"
```
commit -m "First commit"
```
18. Run **sh run.sh** in the terminal. Has the executable file (**main.exe** or **main**) been ignored?
```
sh run.sh
```
The executable file should be ignored by git

19. Run **git log**. Change the message of the last commit to "**Created main.c and run.sh**
```
git commit --amend -m "Created main.c & run.sh"
```
20. Add a **note** *The program and its compilation*, to the last commit.
```
git notes add -m "The program and its compilation"
```
