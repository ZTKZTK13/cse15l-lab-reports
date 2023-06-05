# **Lab Report 5**

**Part 1: Debugging Scenario**

Student Question:

![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/25ca22e3-2c00-4a5f-9721-b05368984ac4)
![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/f2542d92-bdd1-48bf-b441-d520b83017bd)
![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/4099fde0-a56b-437f-a7cf-576210754605)

TA Responce:

Thank you for asking this question.
As in image, the error message is `java.lang.ClassNotFoundException: ArrayTests.java`, which means that the program cannot find the class `ArrayTests.java`. Because the error message indicates that the program is looking for a class, the target file cannot be a `.java` file.
Therefore, the first thing might debug the program is to change `ArrayTests.java` to `ArrayTests`, as shown in the figure below:

![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/227d81e5-f166-4aaa-96d1-132b7463dabf)

Then, you may try to run the code by input `bash TestReporter.sh` in the current working directory, which is where the file `TestReporter.sh` at.

By running that file, you may get a result as below:

![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/4edd74ff-762c-4a58-94d6-996abd2137e4)

In this image, although we changed the target file from a `.java` file to a `.class` file, it still shows the same error message.
To check this bug, we might look through the directory structure. According to the image you provided, the directory structure should be as below:

```
../
  someOtherFiles
  ArrayTests.java
  ArrayTests.class
  TestFile/
    TestReporter.sh
```

According to this directory structer, the file `TestReporter.sh` is not at the same directory with the target file `ArrayTests.class`, and this is the reason why the program cannot find the target file even after we fix the target file name.

To fix this, there are multiple choice of solutions. I will provide one as a reference here. You may go to `TestReporter.sh` and change the `CPATH` as in the picture below:

![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/4d405d40-5640-4ffa-9260-c6b13de30c2a)

By doing this, we are telling the program that the library involving Junit test is in the same directory with the current working directory. 
However, actually the library is not in the same directory with `TestReporter.sh`. 
To deal with this, we can add `cd ..` after the `CPATH` line. After that, the program will look like below:

![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/cd7e1cc9-ff7a-4f79-a2ae-d066b06f95a6)

At this time, the program will change the current working directory to the parent directory of `TestFile`, in which the target file `ArrayTest` is at. 
Run the program again by using `bash TestReporter.sh`, you will see the result below:

![image](https://github.com/ZTKZTK13/cse15l-lab-reports/assets/108479377/f9134674-9797-4052-a25e-edea9106d190)

This result should align with the expected result of this program. Hope this helps.

**Part 2: Reflection**

