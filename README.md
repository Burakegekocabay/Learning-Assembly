# Learning-Assembly
Learning Assembly with project based learning system. (from beginner)


# 01 - Register 
"rax", a single x86 register, like the other registers, rax is a container for a small amount of data. You move data into rax with the mov instruction. Instructions are specified as an operator (in this case, mov), and operands, which represent additional data.


In this challenge, you will write your first assembly. You must move the value 90 into rax. Write your program in a file with a .s extension, such as rax-challenge.s (while not mandatory, .s is the typical extension for assembly files)


# 02 - Syscall
In this challenge, we'll learn our first syscall: exit. The exit "syscall" causes a program to exit. By explicitly exiting, we can avoid the crash we ran into with our previous program!


Now, the syscall number of exit is 60. Go and write your first program: it should move 60 into rax, then invoke syscall to cleanly exit!


# 03 - Exit Codes
System calls can take multiple parameters, though exit takes only one: the exit code. "rdi" is the first parameter to a system call is passed via another register. rdi is what we will focus on in this challenge.

In this challenge, you must make your program exit with the exit code of 42. Thus, your program will need three instructions:

1)Set your program's exit code (move it into rdi). <br>
2)Set the system call number of the exit syscall. <br>
3)syscall!
