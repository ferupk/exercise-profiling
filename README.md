# Module 05: Java Profiling

Feru Pratama Kartajaya<br>
2106750351

## Testing/Profiling Results

1. JMeter Results (GUI)
   - `/all-student` (Before Optimization)
     <img src="img\TP1\tp1-rt-gui.jpg">
     <img src="img\TP1\tp1-sr-gui.jpg">
   - `/all-student` (After Optimization)
     <img src="img\TP1\tp1-rt-gui-optimized.jpg">
     <img src="img\TP1\tp1-sr-gui-optimized.jpg">
   - `/all-student-name` (Before Optimization)
     <img src="img\TP2\tp2-rt-gui.jpg">
     <img src="img\TP2\tp2-sr-gui.jpg">
   - `/all-student-name` (After Optimization)
     <img src="img\TP2\tp2-rt-gui-optimized.jpg">
     <img src="img\TP2\tp2-sr-gui-optimized.jpg">
   - `/highest-gpa` (Before Optimization)
     <img src="img\TP3\tp3-rt-gui.jpg">
     <img src="img\TP3\tp3-sr-gui.jpg">
   - `/highest-gpa` (After Optimization)
     <img src="img\TP3\tp3-rt-gui-optimized.jpg">
     <img src="img\TP3\tp3-sr-gui-optimized.jpg">


2. JMeter Results (CLI)
   - `/all-student` (Before Optimization)
     <img src="img\TP1\tp1-cli.jpg">
   - `/all-student` (After Optimization)
     <img src="img\TP1\tp1-cli-optimized.jpg">
   - `/all-student-name` (Before Optimization)
     <img src="img\TP2\tp2-cli.jpg">
   - `/all-student-name` (After Optimization)
     <img src="img\TP2\tp2-cli-optimized.jpg">
   - `/highest-gpa` (Before Optimization)
     <img src="img\TP3\tp3-cli.jpg">
   - `/highest-gpa` (After Optimization)
     <img src="img\TP3\tp3-cli-optimized.jpg">


3. IntelliJ Profiler
   - `/all-student` (Before Optimization)
     <img src="img\profiling\all-student-profiling-before.jpg">
   - `/all-student` (After Optimization)
     <img src="img\profiling\all-student-profiling-after.jpg">
   - `/all-student` (Before-After Comparison, 65.2% improvement)
     <img src="img\profiling\all-student-profiling-compare.jpg">
   - `/all-student-name` (Before Optimization)
     <img src="img\profiling\all-student-name-profiling-before.jpg">
   - `/all-student-name` (After Optimization)
     <img src="img\profiling\all-student-name-profiling-after.jpg">
   - `/all-student-name` (Before-After Comparison, 71.5% improvement)
     <img src="img\profiling\all-student-name-profiling-compare.jpg">
   - `/highest-gpa` (Before Optimization)
     <img src="img\profiling\highest-gpa-profiling-before.jpg">
   - `/highest-gpa` (After Optimization)
     <img src="img\profiling\highest-gpa-profiling-after.jpg">
   - `/highest-gpa` (Before-After Comparison, 62.5% improvement)
     <img src="img\profiling\highest-gpa-profiling-compare.jpg">

4. Summary
   - Test Plan 1 (/all-student): 151520ms optimized down to 4438ms on average
   - Test Plan 2 (/all-student-name): 1905ms optimized to 100ms on average
   - Test Plan 3 (/highest-gpa): 88ms optimized to 11ms on average
   - Profiling 1 (/all-student): 3295ms optimized down to 1148ms on CPU time, ~65.2% upgrade on performance
   - Profiling 2 (/all-student-name): 578ms optimized to 165ms on CPU time, ~71.5% upgrade on performance
   - Profiling 3 (/highest-gpa): 224ms optimized to 84ms on CPU time, ~62.5% upgrade on performance

## Reflection

```
1. What is the difference between the approach of performance testing with JMeter and
profiling with IntelliJ Profiler in the context of optimizing application performance?

2. How does the profiling process help you in identifying and understanding the weak points
in your application?

3. Do you think IntelliJ Profiler is effective in assisting you to analyze and identify
bottlenecks in your application code?

4. What are the main challenges you face when conducting performance testing and
profiling, and how do you overcome these challenges?

5. What are the main benefits you gain from using IntelliJ Profiler for profiling your
application code?

6. How do you handle situations where the results from profiling with Inte lliJ Profiler are
not entirely consistent with findings from performance testing using JMeter?

7. What strategies do you implement in optimizing application code after analyzing results
from performance testing and profiling? How do you ensure the changes you make do
not affect the application's functionality?
```

1. JMeter is intended for testing an application's performance during a live setting. This kind of testing usually
consists of repeated calls to the application's endpoints to see how it performs when put on varying levels of load.
This type of testing is useful to test the general performance of an application be it through latency, throughput, or
other metrics. However, this type of test does not immediately reveal which part of an application might be causing
bad performance. Meanwhile, the IntelliJ Profiler is used to test individual components, methods, and processes. Profiling
an application provides more information on the performance of each process that happens during its runtime. This allows
developers to clearly see which parts of code are affecting performance and in need of optimization.


2. Through the profiling process, we are able to neatly see the amount of resources that each process takes to complete
its task (memory, CPU time, and others). By going through this information, we can find bottlenecks in our program
and optimize our code accordingly.


3. I've found the IntelliJ Profiler to be very effective at helping me identify bottlenecks in my code. The profiler
provides multiple ways to visualize the application's processes such as through a flame graph, a list of called methods,
a tree structure, and more. Each process is provided with information in terms of the resources such as CPU usage, memory
allocation, and execution time. Different snapshots can also be compared against one another to help visualize the performance
difference between implementations of code.


4. A huge challenge that I faced when conducting the performance testing and profiling comes from processing the data
given through those tests. At first, the amount of information given from even one profiling snapshot was quite overwhelming.
My solution to this problem was to take the time to understand each part of the data. Another thing I was worried about was
inconsistent testing due to my device's performance. I managed this problem by running tests multiple times so that I could
be sure of the true performance of my application.


5. The main benefits of using IntelliJ Profiler comes from its integration to the IntelliJ IDE. It serves as a quick and
convenient way of figuring out possible bottlenecks in code through thorough recording of processes during runtime. Being
able to save past profiling sessions as "Snapshots" also helps when comparing the performance of code before and after
refactoring.


6. If there's inconsistency between the findings of profiling and JMeter testing, I would first review my test plans for
JMeter testing to see if the settings that have been made is able to properly measure the application's performance. If
I'm sure that there's no faults in both the test plans and the profiler, I would make sure that the testing conditions
for both types of testing are as similar as possible. This is done so that either test won't be affected by outside circumstances
that might not affect the other test. Things I've done during testing that fall under this would be making sure that no
other applications are running during testing, as well as doing all tests while my device is charged.


7. The first thing I think about when trying to optimize code is to see whether there are unnecessary processes that could
be cut from execution. An example of this would be the getAllStudentsWithCourses method. In the previous implementation,
a nested for-loop is used to create the list of StudentCourse objects. This takes a huge amount of processing time and was
the biggest bottleneck in the entire application. However, this implementation was actually redundant as the same process
could be done by simply fetching the contents of the StudentCourseRepository.
<br>
If there is no unnecessary code that could be removed, I would then try and figure out alternative solutions to the implementation
that already exists. This can be seen in my implementation of the joinStudentNames method. Simply changing the use of a
StringBuilder object to build the result instead of a normal String makes a significant difference in performance.
<br>
To ensure the correctness of the program, I would compare the query results between the old and new implementation as I
refactor my code.