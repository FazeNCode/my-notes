<h2> What is Segmentation fault in C/C++ ?</h2>
<br>

SegFault (Access Violation) is an error that occurs when a program attempts to retrive or modify the memory, that it does not have permission to access.



<h2> What is GCC? <h/2>
<br>
Gnu Comipler Collection is a open-source comipler system  which is used to comiple variety languages, such as C/C++, GO, Assembly, ADA, Rust, and more, also contains various libraries, such as glibc libgc GDB 


Compilation Process:
- Preprocessing: Handles tasks which include header files, macro expansion and conditional compilation
- Compilation: Preproccessed soruce code is translated


<h2>What is GDB? </h2> 
Gnu Debugger helps developers analyze and debug programs writtin in various programming lanaguge, such as 
C / C++. Allowing user to inspect the behavior of a program durring execution, examine variables, and skim through code to find errors.


<h2> What is a MakeFile? </h2>
<br>
Makefile is utilized for running multiple c and or, c++ script files for automated tasks, without the need to call each indivdual ".cpp" file in the command.

<h3>What is .cpp? </h3>
.cpp is a filename extension which stands for, C Plus Plus

<h2> What's the use case? </h2>
Scanerio: The command below compiles the "main.cpp" file and outputs it to "runfile" as an executable.

```
g++ main.cpp -o runfile
```
To run the executable, you simply call it by ./runfile, which is simple enough, right?

Now lets say we have multiple ".cpp" files that contain different function calls, for specific tasks.
we would need to compile each file in the command, to ouput towards the executable, for example

```
g++ main.cpp func.cpp comp.cpp item.cpp -o runfile 
```