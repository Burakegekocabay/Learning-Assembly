# Learning-Assembly
Learning Assembly with project based learning system. (from beginner)


## 📘 01 - Register

In this first challenge, we introduce the `rax` register — one of the general-purpose 64-bit registers in x86-64.

Like other registers, `rax` can hold a small amount of data. You use the `mov` instruction to transfer data into a register.

**Instructions** are written as an **operator** (such as `mov`) followed by one or more **operands** (which provide the data or destination).

> 🧪 **Challenge**: Move the value `90` into the `rax` register.


## 🚪 02 - Syscall
Now we learn how to **exit a program** properly using a system call (syscall).

A syscall is a way to ask the operating system to do something for your program. In Linux, each syscall has a unique number.

For example, the syscall number for `exit` is `60`.

To make a syscall:
- Move the syscall number into `rax`
- Call `syscall`

> 🧪 **Challenge**: Move `60` into `rax` and call `syscall` to exit cleanly.


## 🔢 03 - Exit Codes

System calls often take parameters. The `exit` syscall takes **one parameter**: the **exit code**.On Linux, the **first parameter** to a syscall is passed using the `rdi` register.

> 🧪 **Challenge**: In this challenge, you must make your program exit with the exit code of `42`.  
> Thus, your program will need **three instructions**:
>
> 1. Set your program's exit code (move it into `rdi`)  
> 2. Set the system call number of the `exit` syscall (move `60` into `rax`)  
> 3. Call `syscall` to exit the program

## 🏁 04 - Execution

Your `.s` (assembly) file contains the code — but for the assembler and linker to process it properly, **you need a few extra lines**.

We are using the **Intel Assembly syntax**, not the default AT&T syntax.  
Also, we must define the **program's entry point** with the proper label and make it visible globally.

You need to add **three key lines** at the top of your file:

1. `.intel_syntax noprefix`  
2. `.global _start`  
3. `_start:`


To compile and run your Assembly programs on Linux:

```bash
as -o program.o <file>.s     # assemble the file
ld -o program program.o      # link it into an executable
./program                    # run the program
echo $?                      # check the exit code
```

> 🧪 Challenge:
>
>Assemble your program using `as`
>
>Link it using `ld`
>
>Run the resulting executable
>
>Verify the exit code with `echo $?`
>
>Make sure your program exits with the expected code (e.g., 42)!
