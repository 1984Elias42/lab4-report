# Lab report 4
## Done Quick
Today, I will use some shortcut of the command line to speedy up my git work.
## Setup
__First__,I will use make a fork to the given repository which is [Link](https://github.com/ucsd-cse15l-w23/lab7), and then start the timer.
__Then__,I will log into my ieng6 account and clone the fork of that repository from my Github account.
For this part, I will use up arrow to call my command history to speed this process up, and the command line should be like this:
```
# fixed code
Keys pressed: <up><up><up><enter>, <up><up><enter>

steve@MSI MINGW64 ~/Documents/GitHub/lab7 (main)
$ ssh cs15lwi23avn@ieng6.ucsd.edu
Last login: Wed Feb 15 16:23:26 2023 from its-cseb260-15.ucsd.edu
Hello cs15lwi23avn, you are currently logged into ieng6-201.ucsd.edu

You are using 0% CPU on this system

Cluster Status 
Hostname     Time    #Users  Load  Averages  
ieng6-201   21:05:02   46  0.84,  1.36,  1.45
ieng6-202   21:05:01   43  1.31,  1.29,  1.10
ieng6-203   21:05:01   42  0.21,  0.48,  0.54


        *** SDSC Core Network Upgrade ***
        2023-03-07 19:00 - 2023-03-08 03:00
This work is now complete. If there were any disruptions to your
work or notice any problems that may have been caused by the network
upgrades please report them to the service desk.

https://support.ucsd.edu/its


 
Mon Mar 13, 2023  9:09pm - Prepping cs15lwi23
[cs15lwi23avn@ieng6-201]:~:363$ mkdir LAB7
[cs15lwi23avn@ieng6-201]:~:364$ cd LAB7
[cs15lwi23avn@ieng6-201]:LAB7:365$ git clone git@github.com:ucsd-cse15l-w23/lab7.git
Cloning into 'lab7'...
remote: Enumerating objects: 35, done.
remote: Total 35 (delta 0), reused 0 (delta 0), pack-reused 35
Receiving objects: 100% (35/35), 372.19 KiB | 1.39 MiB/s, done.
Resolving deltas: 100% (12/12), done.
[cs15lwi23avn@ieng6-201]:LAB7:366$ 
```
Here is the screenshot:
![Image](https://github.com/1984Elias42/lab4-report/blob/main/1.png)
## Test the code
I will use copy and paste command to speed up my process, I will copy the needed command to run the test. And here is how command looks like:
```
# fixed code
Keys pressed: <Ctrl-V><enter>, <Ctrl-V><enter>

[cs15lwi23avn@ieng6-201]:lab7:370$ javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
[cs15lwi23avn@ieng6-201]:lab7:371$ java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests
JUnit version 4.13.2
..E
Time: 0.523
There was 1 failure:
1) testMerge2(ListExamplesTests)
org.junit.runners.model.TestTimedOutException: test timed out after 500 milliseconds
        at ListExamples.merge(ListExamples.java:43)
        at ListExamplesTests.testMerge2(ListExamplesTests.java:19)

FAILURES!!!
Tests run: 2,  Failures: 1

[cs15lwi23avn@ieng6-201]:lab7:372$ JUnit version 4.13.2
```
And here is my screenshot for this process:
![Image](https://github.com/1984Elias42/lab4-report/blob/main/2.png)
## Debug and test again
I will look at the code by using up arrow to call my history command which is cat command and try to find the bug, then I will use copy and paste to edit the code to fix the bug and run the tester again and see if it works. Here is the command be like:
```
# fixed code
Keys pressed: <up><enter>, <Ctrl-V><enter>, <Ctrl-V><enter>,<up><up><up><enter>

[cs15lwi23avn@ieng6-201]:lab7:372$ cat ListExamples.java
import java.util.ArrayList;
import java.util.List;

interface StringChecker { boolean checkString(String s); }

class ListExamples {

  // Returns a new list that has all the elements of the input list for which
  // the StringChecker returns true, and not the elements that return false, in
  // the same order they appeared in the input list;
  static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0, s);
      }
    }
    return result;
  }


  // Takes two sorted list of strings (so "a" appears before "b" and so on),
  // and return a new list that has all the strings in both list in sorted order.
  static List<String> merge(List<String> list1, List<String> list2) {
    List<String> result = new ArrayList<>();
    int index1 = 0, index2 = 0;
    while(index1 < list1.size() && index2 < list2.size()) {
      if(list1.get(index1).compareTo(list2.get(index2)) < 0) {
        result.add(list1.get(index1));
        index1 += 1;
      }
      else {
        result.add(list2.get(index2));
        index2 += 1;
      }
    }
    while(index1 < list1.size()) {
      result.add(list1.get(index1));
      index1 += 1;
    }
    while(index2 < list2.size()) {
      result.add(list2.get(index2));
      index1 += 1;
    }
    return result;
  }


}
$ java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ListExamplesTests
JUnit version 4.13.2
..
Time: 0.019

OK (2 tests)
```
And that is the screenshot looks like:
![Image](https://github.com/1984Elias42/lab4-report/blob/main/3.png)
![Image](https://github.com/1984Elias42/lab4-report/blob/main/4.png)
## 3. Conclusion
Before this lab, I used to type everything by myself in the command area and that waste a lot of time, after this lab I learned some shortcut in the command line such as up and down arrow to call the history command line, and these shortcut can really save me a lot of time , to speed up my work.

