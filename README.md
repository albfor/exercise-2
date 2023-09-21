# Exercise 2

## Walkthrough

1. Make a dir, **exercise-2**, and open it in vscode.
```shell
mkdir exercise-2 && code exercise-2
```
2. Open the terminal of vscode and create a repository and run **git status** and **git log**
```shell
git init
```
```shell
git status
```
```shell
git log
```
3. Create **README.md** and write **# Exercise 2**
```shell
echo "# Exercise 2" > README.md
```
4. Create **.gitignore** and ignore all **.txt** files.
```shell
echo "*.txt" > .gitignore
```
5. Add changes to the staging area
```shell
git add .
```
6. Make a commit with the message "Init commit"
```shell
git commit -m "Init commit"
```
7. Run **git status**, **git log** and **git log --oneline**.
```shell
git status
```
```shell
git log
```
```shell
git log --oneline
```
8. Remove **README.md** using **git rm**
```shell
git rm README.md
```
9. Run ** git status** and then unstage the change using **git restore**
```shell
git status
```
```shell
git restore --staged README.md
```
10. Run **git status** and **discard** the changes using **git restore**
```shell
git status
```
```shell
git restore README.md
```
11. Instead of all **.txt** files, ignore all files without **.c, .md** or **.sh** extensions.

Open your .gitignore file with a text editor and change the content to 
```
# Ignores every file
*

# Excludes every file with the .c extensions from the ignore
!*.c
# Excludes every file with the .sh extensions from the ignore
!*.sh
# Excludes every file with the .md extensions from the ignore
!*.md
```
or if you want to use printf 
```shell
printf '*\n!*.c\n!*.md\n!*.sh' > .gitignore
```
12. Run **git status** and add **.gitignore** 
```shell
git status && git add .gitignore
```
13. Create two files, **main.c** and **run.sh**
```shell
touch main.c run.sh
```
14. Write the below code with printf to run.sh

clear && gcc main.c -o main && ./main
```shell
printf "clear && gcc main.c -o main && ./main" > run.sh
```
15. Write the below code with printf to main.c

#include <stdio.h>\n\nint main(void) \n{\n\treturn 0;\n}
```shell
printf "#include <stdio.h>\n\nint main(void) \n{\n\treturn 0;\n}" > main.c
```
Alternatively, open main.c with a text editor and type the following:
```c
#include <stdio.h>

int main(void)
{
	return 0;
}
```
16. Run **git status** and add changes to staging area.
```shell
git status
```
![git status](git-status.png)
```shell
git add .
```
17. **Commit** changes with the message "**First commit**"
```shell
commit -m "First commit"
```
18. Run **sh run.sh** in the terminal. Has the executable file (**main.exe** or **main**) been ignored?
```shell
sh run.sh
```
The executable file should be ignored by git

![main is ignored](gitignore.png)

19. Run **git log**. Change the message of the last commit to "**Created main.c and run.sh**
```shell
git commit --amend -m "Created main.c & run.sh"
```
20. Add a **note** *The program and its compilation*, to the last commit.
```shell
git notes add -m "The program and its compilation"
```
21. Create a **branch**, *feature-branch*, based on the *master* branch.
```shell
git branch feature-branch
```
22. Create another **branch**, *print-1-6-1*, based on the *master* branch.
```shell
git branch print-1-6-1
```
23. Get the list of branches using **git branch**
```shell 
git branch
```
24. **Rename** *feature-branch*  to **print-1-3-1**
```shell
git branch feature-branch -m print-1-3-1
```
25. Get the list of branches using **git branch**
```shell 
git branch
```
26. **Switch** to **print-1-3-1** branch and run **git log --oneline**
```shell
git switch print-1-3-1
```
```shell
git log --oneline
```
27. In **main.c** make a program using a **for loop** to **print from 1 to 3** to the output.

open main.c with a text editor and change the content to:
```c
#include <stdio.h>

int main(void)
{
	for (int i = 1; i < 4; i++)
	{
		printf("%d ", i);
	}
	printf("\n");

	return 0;
}
```
28. Run **sh run.sh** in the **terminal** to make sure the program works.
```shell
sh run.sh
```
should print ```1 2 3 ``` to the console.

29. Run **git status** and **add** the changes to the staging area.
```shell
git status
```
```shell
git add .
```
30. **Commit** the changes with the message "**print from 1 to 3**". Run **git log --oneline**.
```shell
git commit -m "print from 1 to 3"
```
```shell
git log --oneline
```
31. Now **switch** to *master* and run **git log --oneline**
```shell
git switch master
```
```shell
git log --oneline
```
32. What is the **difference** between *master* and *print-1-3-1*?

`git diff <branch-name>` will print out all the differences between our 
current branch and <branch-name>.
```shell
git diff print-1-3-1
```
33. **Switch** to *print-1-3-1* and run **git status**
```shell
git switch print-1-3-1 && git status
```
34. In **main.c** make a **for loop** after the previous loop to **print from 2 to 1** to the output

open main.c with a text editor and change the content to:
```c
#include <stdio.h>

int main(void)
{
	for (int i = 1; i < 4; i++)
	{
		printf("%d ", i);
	}

	for (int i = 2; i > 0; i--)
	{
		printf("%d ", i);
	}
	printf("\n");

	return 0;
}
```
35. Run **sh run.sh** in the **terminal** to make sure it runs.
```shell
sh run.sh
```
36. **Commit** the changes with the message "**print from 2 to 1**" and run **git log --oneline**
```shell
git commit -a -m "print from 2 to 1" && git log --oneline
```
37. In the last loop change your code in order to print from **12 to 1**.

open main.c with a text editor and change the content to:
```c
#include <stdio.h>

int main(void)
{
	for (int i = 1; i < 4; i++)
	{
		printf("%d ", i);
	}

	for (int i = 12; i > 0; i--)
	{
		printf("%d ", i);
	}
	printf("\n");

	return 0;
}
```
38. Run **sh run.sh** in the **terminal** to make sure the program works.
```shell
sh run.sh
```
39. **Commit** the changes with the message "**print from 12 to 1**" and run **git log --oneline**
```shell
git commit -m "print from 12 to 1" && git log --oneline
```
40. **Revert** the last commit with the message "**Revert print from 12 to 1**". Run **git log --oneline**
