### Task 1: ###

## **Aim:Create a C file and compile the file using both GCC Compiler and RISCV Compiler.** ##


  # **Step 1**:
	open terminal and create a file named sum1ton.c using leafpad              

  # Step 2: 
	Write a simple c program to find the the sum of first n integers in the sum1ton.c file.
  
  ![Code_Snippet](https://github.com/user-attachments/assets/b370c658-a92d-4801-9df1-8a8198507aa8)


  # Step 3: 
	 Compile the file using GCC compiler and then Run the file.
  
  ![Task1_1](https://github.com/user-attachments/assets/3ae90c79-bf8f-4aa6-81e6-1bdfa830503e)

  # Step 4: 
	Now Compile the Same Program using RISCV Compiler.

  ![task_2](https://github.com/user-attachments/assets/1a909b7a-9642-4e28-8200-5e1127e8314a)
  # Step 5:
	Compile using O1 command and search for main function and calculate the no of steps taken,we can see that it took 15 steps.
 
  ![task2](https://github.com/user-attachments/assets/7bfeeffa-a5d4-4220-bf02-33743b930b15)
	
# Step 6:
 
  Compile using Ofast Command and search for main function and calculate the no of steps taken,we can see that it took 12 steps.
	
![task_2_2](https://github.com/user-attachments/assets/add80aeb-74cf-4ec5-a05d-95c4330d0206)
# ASIC Lab2 
## Aim: 
To compile a file using RISCV compiler and verifying it with GCC compiler

## Step1: 
Compile the sum1ton.c file using GCC compiler using the following commands.
```
gcc sum1ton.c
./a.out
```
## Step2: 
Compile the sum1ton.c file using RISCV compiler using the following commands.
```
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
spike pk sum1ton.o
```
## Step3:
Start debugging the file with the help of object dump file using the following commands
```
spike -d pk sum1ton.o
```
![Spike_2](https://github.com/user-attachments/assets/291ea977-3ea3-4613-8d99-22e7e18f73c7)
## Step4:
Observe the change value of registers before compiling and after compiling using the following commands
```
reg 0 a2
reg 0 a2
reg 0 sp
```
![Spike_1](https://github.com/user-attachments/assets/f48a3734-9a7c-423f-b454-9d066531b921)
# ASIC Lab2 
## Aim: 
To compile a file using RISCV compiler and verifying it with GCC compiler

## Step1: 
Compile the sum1ton.c file using GCC compiler using the following commands.
```
gcc sum1ton.c
./a.out
```
## Step2: 
Compile the sum1ton.c file using RISCV compiler using the following commands.
```
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
spike pk sum1ton.o
```
## Step3:
Start debugging the file with the help of object dump file using the following commands
```
spike -d pk sum1ton.o
```
![Spike_2](https://github.com/user-attachments/assets/291ea977-3ea3-4613-8d99-22e7e18f73c7)
## Step4:
Observe the change value of registers before compiling and after compiling using the following commands
```
reg 0 a2
reg 0 a2
reg 0 sp
```
![Spike_1](https://github.com/user-attachments/assets/f48a3734-9a7c-423f-b454-9d066531b921)
