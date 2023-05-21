# **Lab Report 4**

Key steps to fix the bug with only using commands and the command window in bash script:

* Log into ieng6

  To do this step, we should type in the ieng6 accound by using `ssh` command as it in the figure below:
  
  ![image](image.png)
  
* Clone the fork or the the repository from github

  By using `git clone` command, we can clone a copy of the target repository to the ieng6 account. I used `git clone https://github.com/ucsd-cse15l-s23/lab7` to clone the repository:
  
  ![image](image1.png)
  
  To check the copy repository, `ls` might be helpful:
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/ad81225e-8fbb-45dd-9f6b-57de4c9260af)

* Run the test

  To run the junit test, the first thing to do is to change the current working directory to the copy repository, where I typed `cd lab7` and pressed `<Enter>`to change the working directory.
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/75aa4de2-fc2f-4747-8097-1ec5139a842c)

  To run the junit test, I typed `bash test.sh` and pressed `<Enter>`:
 
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/2f5104ee-a5f4-48f6-9622-4d7b6124ac83)

  The junit test reported failures, which says "timed out". The reason might be there are some infinite loops in the program.
  
* Edit the code file to fix the failing test

  To fix the bugs, let's look at the codes of the program. Type `vim ListExamples.java` and press `<Enter>` to use `vim` to check the original code.
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/7fbb46c2-6cd0-4d39-b7df-cfeb15955c24)

  It should be something like below:
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/65bd336a-f4a7-4782-addc-6fa375efca95)

  Then, hold `h` and `k` until the cursor is at the top left corner of the file, which is important to make sure the searching steps next shows correct answer. Type `/index1` and `<Enter>` to search all the places where the variable `index1` appears, and press `n` 9 times to locate the target variable where the bug is at.
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/b3e65944-c654-4e41-9b8b-923cf5d51865)

  Press `<esc>` to quit to the normal mode, then press `l` 11 times to move the cursor to the `1` of `index1`:
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/1da72321-be78-4b22-b303-36b238f8db7b)

  After that, press `x` to delete the `1` and press `i` to use the insert mode. While in the insert mode, type `2` to make the variable change to `index2`. Press `<esc>` to return to the normal mode.
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/f23382c8-037f-4f73-8256-7711e16572ba)

  When finishing fixing the bug and returing to the normal mode, type `:wq` and press `<Enter>` to save and exit this file. 
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/6b5411f2-66ef-40c2-ba14-8a0130ec7de1)

* Run the test again

  Here, type in `bash test.sh` (and press `<Enter>`) again to run the junit test.
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/7781b8c5-afaa-492e-8197-3fe5add93190)

  The test is passed now, which means the bug is fixed.
  
* Commit and Push

  Before commiting and pushing the file to the github account, use `git status` to check the changed file first:
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/55ddc8e6-0c13-4d37-a1f6-ddeb2fead6ee)

  The file `ListExamples.java` is modified, but it is not added to commit. use `git add ListExamples.java` to add the file to commit. Then use `git status` to check again, the file changed to green, which means it is successfully added to commit:
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/be2551e4-6a1e-4da2-84a0-0af6f71c628f)

  Then, type `git commit` and put some commit message (press `i` to insert) to commit the change:
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/f0557507-511b-46a8-bb24-a2c5e25903f1)

  Press `:wq` to save the commit message.
  
  Last but not least, use `git push` and press `<Enter>` to push the fixed repository to the github account:
  
  ![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/9a03ac9b-4172-4662-8418-9e6f29ea61b8)

  
