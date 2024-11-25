<details>
<summary>ASIC Lab 1</summary>
<br>

## Aim:Create a C file and compile the file using both GCC Compiler and RISCV Compiler. ##


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
</details>
<details>
<summary>ASIC Lab 2</summary> 
<br>

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
</details>
<details>
<summary>ASIC Lab 3</summary>
<br>

### Instructions
```
 ADD r5, r6, r7
 SUB r7, r5, r6
 AND r6, r5, r7
 OR r8, r6, r5
 XOR r8, r5, r4
 SLT r10, r2, r4
 ADDI r12, r3, 5
 SW r3, r1, 4
 SRL r16, r11, r2
 BNE r0, r1, 20
 BEQ r0, r0, 15
 LW r13, r11, 2
 SLL r15, r11, r2
```
### Instruction Table
| Operation       | Type | 32-bit Instruction        | Hexadecimal    |
|-----------------|------|---------------------------|----------------|
| ADD r5, r6, r7  | R    | 0000000 00111 00110 000 00101 0110011 | 0x00B30333  |
| SUB r7, r5, r6  | R    | 0100000 00110 00101 000 00111 0110011 | 0x40A282B3  |
| AND r6, r5, r7  | R    | 0000000 00111 00101 111 00110 0110011 | 0x00F2F2B3  |
| OR r8, r6, r5   | R    | 0000000 00101 00110 110 01000 0110011 | 0x00B301B3  |
| XOR r8, r5, r4  | R    | 0000000 00100 00101 100 01000 0110011 | 0x00A281B3  |
| SLT r10, r2, r4 | R    | 0000000 00100 00010 010 01010 0110011 | 0x004102A3  |
| ADDI r12, r3, 5 | I    | 000000000101 00011 000 01100 0010011  | 0x00518313  |
| SW r3, r1, 4    | S    | 0000000 00011 00001 010 00001 0100011 | 0x00312023  |
| SRL r16, r11, r2| R    | 0000000 00010 01011 101 10000 0110011 | 0x0025C833  |
| BNE r0, r1, 20  | B    | 0000000 00001 00000 001 0000 1100011  | 0x00100263  |
| BEQ r0, r0, 15  | B    | 0000000 00000 00000 000 0000 1100011  | 0x00000063  |
| LW r13, r11, 2  | I    | 000000000010 01011 010 01101 0000011  | 0x0025A293  |
| SLL r15, r11, r2| R    | 0000000 00010 01011 001 01111 0110011 | 0x0025A933  |

## Task2:
## By making use of RISCV Core: Verilog Netlist and Testbench, perform an experiment of Functional Simulation and observe the waveforms

There are some differences between RISCV ISA and Hardcoded ISA.So for the above Instructions the difference between RISCV ISA and Hardcoded ISA is
| Operation           | Standard RISC-V ISA | Standard RISC-V ISA (Binary)               | Hardcoded ISA     | Hardcoded ISA (Binary)                  |
|---------------------|---------------------|--------------------------------------------|-------------------|-----------------------------------------|
| ADD R6, R2, R1      | 32'h00110333        | 000000000001 00010 000 00110 0110011       | 32'h02208300      | 000000100010 00000 100 00000 01100000  |
| SUB R7, R1, R2      | 32'h402083b3        | 010000000010 00000 000 00111 0110011       | 32'h02209380      | 000000100010 01000 100 10000 01100000  |
| AND R8, R1, R3      | 32'h0030f433        | 000000000011 00000 111 01000 0110011       | 32'h0230a400      | 000000100011 01000 101 00100 01100000  |
| OR R9, R2, R5       | 32'h005164b3        | 000000000101 00010 110 01001 0110011       | 32'h02513480      | 000000100101 00010 110 10100 01100000  |
| XOR R10, R1, R4     | 32'h0040c533        | 000000000100 00000 100 01010 0110011       | 32'h0240c500      | 000000100100 00000 100 11000 01100000  |
| SLT R1, R2, R4      | 32'h0045a0b3        | 000000000100 00010 010 00001 0110011       | 32'h02415580      | 000000100100 00010 101 01010 01100000  |
| ADDI R12, R4, 5     | 32'h004120b3        | 000000000101 00010 010 01100 0010011       | 32'h00520600      | 000000100100 00010 010 00010 01100000  |
| BEQ R0, R0, 15      | 32'h00000f63        | 000000000000 00000 000 00000 1100011       | 32'h00f00002      | 000000000000 00000 000 00000 11000000  |
| SW R3, R1, 2        | 32'h0030a123        | 000000000011 00000 010 00001 0100011       | 32'h00209181      | 000000100010 00000 010 00001 01100000  |
| LW R13, R1, 2       | 32'h0020a683        | 000000000010 00000 010 01101 0000011       | 32'h00208681      | 000000100010 00000 010 01100 01100000  |
| SRL R16, R14, R2    | 32'h0030a123        | 000000000011 00000 010 00001 0100011       | 32'h00271803      | 000000100010 00000 011 00110 01100000  |
| SLL R15, R1, R2     | 32'h002097b3        | 000000000010 00000 111 01111 0110011       | 32'h00208783      | 000000100010 00000 111 01111 01100000  |
### Step1:
Copy the code from the reference github repo and paste it in your verilog and testbench file
Use the following commands for running and simulating of verilog code:
![0](https://github.com/user-attachments/assets/d4ca1e9b-7337-402a-bbd8-582e33e686f8)
Waveforms for the instructions are
```
Instruction 1: ADD R6, R2, R1
```
![1](https://github.com/user-attachments/assets/3761c3f4-dfa0-43c5-a1a7-a621420d5f33)
```
Instruction 2: SUB R7, R1, R2
```
![2](https://github.com/user-attachments/assets/96d47522-c716-480e-9e54-86b54aa39165)
```
Instruction 3: AND R8, R1, R3
```
![3](https://github.com/user-attachments/assets/953ff3af-3571-4cc5-9cdc-337462a5af8b)
```
Instruction 4: OR R9, R2, R5
```
![4](https://github.com/user-attachments/assets/2282d2c5-9ca2-413e-a670-9781f90d6ba3)
```
Instruction 5: XOR R10, R1, R4
```
![5](https://github.com/user-attachments/assets/bb42be7f-b9bf-4bb8-a47d-82670867f15f)
```
Instruction 6: SLT R1, R2, R4
```
![6](https://github.com/user-attachments/assets/79ce7d65-4a54-43f0-8144-e10eece07185)
```
Instruction 7: ADDI R12, R4, 5
```
![7](https://github.com/user-attachments/assets/fe19573d-a6ac-4f63-b4da-8e11d3a4cb6c)
```
Instruction 8: BEQ R0, R0, 15
```
![8](https://github.com/user-attachments/assets/418e1f1d-2e18-4b53-bf43-b0e5c295da2e)
</details>
<details>
<summary>ASIC Lab 4</summary>
<br>

## Task:Compile a C application with GCC and RISC-V GCC ##
### Application Name : File Management System ###
Description :
The File Management System is an in-memory simulation for basic file operations, including creation, writing, reading, and deletion of files. It provides a text-based menu interface where users can enter numeric choices to perform actions. Files are simulated using a data buffer, and user input for filenames and text is handled appropriately. The system ensures that operations are only performed on existing files and includes error handling for invalid input. It’s a useful tool for understanding file handling concepts without interacting with the actual file system.
### Here is the C program for File Management System: ###
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_DATA_SIZE 1024
#define MAX_FILENAME_SIZE 256
typedef struct {
    char data[MAX_DATA_SIZE];
    size_t size;
    int exists;
    char filename[MAX_FILENAME_SIZE];
} InMemoryFile;

InMemoryFile simulatedFile = { .size = 0, .exists = 0 };

void createFile();
void writeFile();
void readFile();
void deleteFile();
void clearInputBuffer();

int main() {
    int choice;

    while (1) {
        printf("\nFile Management System\n");
        printf("1. Create File\n");
        printf("2. Write to File\n");
        printf("3. Read from File\n");
        printf("4. Delete File\n");
        printf("5. Exit\n");
        printf("Enter your choice: ");

        if (scanf("%d", &choice) != 1) {
            clearInputBuffer();
            printf("Invalid input. Please enter a number.\n");
            continue;
        }
        clearInputBuffer();

        switch (choice) {
            case 1:
                createFile();
                break;
            case 2:
                writeFile();
                break;
            case 3:
                readFile();
                break;
            case 4:
                deleteFile();
                break;
            case 5:
                printf("Exiting the program.\n");
                exit(0);
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }

    return 0;
}

void createFile() {
    if (!simulatedFile.exists) {
        printf("Enter filename to create: ");
        fgets(simulatedFile.filename, MAX_FILENAME_SIZE, stdin);
        size_t len = strlen(simulatedFile.filename);
        if (len > 0 && simulatedFile.filename[len - 1] == '\n') {
            simulatedFile.filename[len - 1] = '\0';
        }
        
        simulatedFile.size = 0;
        memset(simulatedFile.data, 0, MAX_DATA_SIZE);
        simulatedFile.exists = 1;
        printf("File '%s' created successfully in memory.\n", simulatedFile.filename);
    } else {
        printf("File '%s' already exists in memory.\n", simulatedFile.filename);
    }
}

void writeFile() {
    if (simulatedFile.exists) {
        char data[256];
        printf("Enter text to write to file (end with an empty line):\n");
        simulatedFile.size = 0;
        memset(simulatedFile.data, 0, MAX_DATA_SIZE);
        while (fgets(data, sizeof(data), stdin) && data[0] != '\n') {
            size_t len = strlen(data);
            if (simulatedFile.size + len < MAX_DATA_SIZE) {
                strncat(simulatedFile.data, data, MAX_DATA_SIZE - simulatedFile.size - 1);
                simulatedFile.size += len;
            }
        }
        printf("Data written to '%s'.\n", simulatedFile.filename);
    } else {
        printf("Cannot write to file. File does not exist in memory.\n");
    }
}

void readFile() {
    if (simulatedFile.exists && simulatedFile.size > 0) {
        printf("Content of '%s':\n%s", simulatedFile.filename, simulatedFile.data);
    } else if (simulatedFile.exists) {
        printf("File '%s' is empty.\n", simulatedFile.filename);
    } else {
        printf("File does not exist in memory.\n");
    }
}

void deleteFile() {
    if (simulatedFile.exists) {
        simulatedFile.size = 0;
        memset(simulatedFile.data, 0, MAX_DATA_SIZE);
        simulatedFile.exists = 0;
        printf("Simulated file '%s' deleted.\n", simulatedFile.filename);
    } else {
        printf("No file to delete. File does not exist in memory.\n");
    }
}

void clearInputBuffer() {
    int c;
    while ((c = getchar()) != EOF && c != '\n');
}
```
### Compiling the program using GCC Compiler ###
First create a file and write the above c program in it.
We can compile the program using GCC compiler by giving the following commands:
```
gcc file.c
./a.out
```
### Results using the GCC compiler ###
![4_1](https://github.com/user-attachments/assets/e3222a68-ba7f-4b16-8008-83f3edcd460f)

### Compiling the program using RISC-V GCC Compiler ###
We can compile the program using RISC-V GCC compiler by giving the following commands:
```
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i file.c
spike pk a.out
```
### Results using the RISC-V GCC compiler  ###
![4_2](https://github.com/user-attachments/assets/b73f7b93-8315-41a2-b8b2-33a1243a3ff2)

### Here we can see that outputs of both GCC and RISC-V GCC compiler matches ####
</details>
<details>
<summary>ASIC Lab 5</summary>
<br>

# Building a five stage pipelining RISC-V processor core #
This repository features a 5-stage pipelined RISC-V core built using TL-Verilog (Transactional Verilog). TL-Verilog enhances the design process by emphasizing data transactions and pipeline efficiency, making it ideal for creating scalable and modular hardware designs. This project demonstrates the implementation of a RISC-V core, highlighting the advantages of TL-Verilog in modern CPU design. Explore the code to see how TL-Verilog facilitates the construction of a pipelined architecture.
<details>
	<summary>Day 3</summary>
	<br>

 
<details>
<summary>Digital Combinational Circuits Implementation</summary>
<br>

 ## Combinational Circuit Implementation ##
 ### Inverter : ### 
In a combinational circuit, an inverter (NOT gate) is a fundamental logic gate that flips the input signal, outputting the opposite value.
 Here is the implementation of an Inverter using TL Verilog
 #### Logic: ####
 ```
 $out = ! $in1;
 ```
![inverter](https://github.com/user-attachments/assets/dde0bec5-0422-4c53-ad5a-dd38dc229c88)
### Vector : ###
 In TL-Verilog, a vector represents a collection of bits grouped together, allowing for efficient manipulation of multi-bit signals. Vectors are essential for handling wide data paths and operations in 
 transactional-level designs.
 Here is the implementation of an Vector using TL Verilog
 #### Logic: ####
 ```
 $out[4:0] = $in1[3:0] + $in2[3:0];
 ```
![Vector](https://github.com/user-attachments/assets/5820ce9a-51da-408e-b1c8-c37983576c40)
### MUX : ###
A multiplexer (MUX) is a digital switch that selects one of several input signals and routes it to a single output line based on control signals. It efficiently manages multiple data sources, enabling the implementation of complex routing and decision-making functions in circuits.
Here is the implementation of an MUX using TL Verilog
#### Logic: ####
```
$out[7:0] = $sel ? $in1[7:0] : $in2[7:0];
```
![Mux_vector](https://github.com/user-attachments/assets/047a4ce4-b505-48f0-a12f-782c345889d0)
### Combinational Calculator : ###
The combinational calculator is designed using a 4-to-1 multiplexer (MUX) and is capable of performing fundamental operations such as addition, subtraction, multiplication, and division.
![Cal_logic_com](https://github.com/user-attachments/assets/daa5e16a-832f-4958-83ad-72855052a136)

#### Logic: ####
```
   $val1[31:0] = $rand1[3:0];
   $val2[31:0] = $rand2[3:0];
   
   $add[31:0] =  $val1[31:0] +  $val2[31:0];
   $min[31:0] =  $val1[31:0] -  $val2[31:0];
   $mul[31:0] =  $val1[31:0] *  $val2[31:0];
   $div[31:0] =  $val1[31:0] /  $val2[31:0];
   
   $out[31:0] = $sel[1] ? ($sel[0] ? $div[31:0] : $mul[31:0])
                        : ($sel[0] ? $min[31:0] : $add[31:0]);
```
TL Code & Waveform for the Combinational Calculator:
![calc_comb](https://github.com/user-attachments/assets/f9f1d2fe-9d11-4187-90d6-9a1d789ad22a)
</details>
<details>
	<summary>Digital Sequential Circuit Implementation</summary>
	<br>
	
 ## Sequential Circuit Implementaion ##
 ### Counter ###
A counter is a digital circuit that sequentially counts through a series of states, typically used for counting events or generating specific time delays. It can be implemented as either a binary counter, which counts in binary increments, or a decade counter, which counts from 0 to 9.
#### Logic: ####
```
$out[31:0] = $reset ? 1 : (>>1$out + 1);
```
Here is the TL code and output wave form for the counter
![Counter](https://github.com/user-attachments/assets/d3d68363-943d-472d-ba4e-32b6d6f7d438)

 ### Fibinacci Sequence : ###
 The Fibonacci sequence is a series where each number is the sum of the two preceding ones, starting with 0 and 1; for example, the sequence begins 0, 1, 1, 2, 3, 5, 8, and so on.
 #### Logic ####
 ```
$out[31:0] = $reset ? 1 : (>>1$out + >>2$out);
```
![Fibnacci](https://github.com/user-attachments/assets/723a4296-58c1-4ae7-9da5-ce744661176c)
### Seuential calculator : ###
A sequential calculator processes operations in a step-by-step fashion, with each operation relying on the results of the previous one, making the output of one step the input for the next.
A sequential calculator can be realized using a 4-to-1 multiplexer (MUX) and a flip-flop to store the current out[31:0] data. Additionally, a reset signal ensures that the calculator outputs 32'b0 when the reset is activated.
![Seq_cal_log](https://github.com/user-attachments/assets/52d171cb-533f-4940-a58e-a0dd61c7980a)

#### Logic: ####
```
   $val1[31:0] = $rand1[3:0];
   $val2[31:0] = >>1$out[31:0];
   $op[1:0] = $rand2[1:0];
   
   $sum[31:0] = $val1[31:0] + $val2[31:0];
   $diff[31:0] = $val1[31:0] - $val2[31:0];
   $prod[31:0] = $val1[31:0] * $val2[31:0];
   $quot[31:0] = $val1[31:0] / $val2[31:0];
   
   $out[31:0] = $reset ? 32'b0 : (($op[1:0]==2'b00) ? $sum :
                                       ($op[1:0]==2'b01) ? $diff :
                                          ($op[1:0]==2'b10) ? $prod : $quot);
   
   `BOGUS_USE($out);
   `BOGUS_USE($reset);
```
Here is the TL code and Wave form of the Sequential calculator
![seq_calc](https://github.com/user-attachments/assets/1b50ca7a-a2d6-4fa8-ad53-30c28f0388f9)
</details>
<details>
	<summary>Pipelining</summary>
	<br>

 ## Pipe lining: ##
Pipelining is a technique used in computer architecture to improve instruction throughput by overlapping the execution of multiple instructions. In a pipelined processor, different stages of instruction processing (such as fetching, decoding, executing, and writing back) are performed in parallel. This approach increases overall performance by allowing the CPU to work on several instructions simultaneously, reducing the time needed to execute a sequence of instructions. However, pipelining introduces complexities such as data hazards and control hazards that must be managed to maintain efficiency.

Calculator is implemented with pipelining
 #### Logic: ####
 ```
 |calc
      @1
         $input1[31:0] = $rand1[3:0];
         $input2[31:0] = >>1$result;

         $sum[31:0] = $input1 + $input2;
         $difference[31:0] = $input1 - $input2;
         $product[31:0] = $input1 * $input2;
         $quotient[31:0] = $input2 != 0 ? $input1 / $input2 : 32'b0;
         
         $result[31:0] = $reset ? 32'b0 : 
                          ($op[1] ? ($op[0] ? $quotient : $product) : 
                                    ($op[0] ? $difference : $sum));

         $count[31:0] = $reset ? 32'b0 : >>1$count + 1;
```
Here is the TL code and output wave form
![pipe_calc](https://github.com/user-attachments/assets/6d636555-8774-41ca-abfc-6a15292c7f20)

The same calculator circuit can be implemented with pipelining across two clock cycles. In the first clock cycle, we perform addition, subtraction, multiplication, and division on the two input values. In the second clock cycle, we select the appropriate operand to produce the final output.
#### Logic:####
```
 |calculator
      @1
         $input1[31:0] = $rand1[3:0];
         $input2[31:0] = >>1$intermediate_result;

         $addition[31:0] = $input1 + $input2;
         $subtraction[31:0] = $input1 - $input2;
         $multiplication[31:0] = $input1 * $input2;
         $division[31:0] = $input2 != 0 ? $input1 / $input2 : 32'b0; // Prevent division by zero

         $counter[31:0] = $reset_signal ? 32'b0 : >>1$counter + 1;
      
      @2
         $final_output[31:0] = $reset_signal ? 32'b0 : 
                               ($operation[1] ? 
                                ($operation[0] ? $division[31:0] : $multiplication[31:0]) :
                                ($operation[0] ? $subtraction[31:0] : $addition[31:0]));
```
Here is the TL code and output Waveform
![image](https://github.com/user-attachments/assets/1e09fba7-1556-4a2c-aa7f-833835bfdcb8)
</details>
<details>
	<summary>Validity</summary>
	<br>

 ## Validity ##
Validity is a feature in TL-Verilog that is asserted to indicate whether a transaction in a pipeline is valid or true. The introduction of a new scope, known as the "when" scope, denoted as ?$valid, enhances design efficiency. This scope offers several advantages, including simplified debugging, a cleaner design, improved error checking, and automated clock gating.

Implementation of calculator with validity
#### Logic: ####
```
|calc
      @0
         $reset = *reset;
         
      @1
         $val1 [31:0] = >>2$out [31:0];
         $val2 [31:0] = $rand2[3:0];
         
         $valid = $reset ? 1'b0 : >>1$valid + 1'b1 ;
         $valid_or_reset = $valid || $reset;
         
      ?$vaild_or_reset
         @1   
            $sum [31:0] = $val1 + $val2;
            $diff[31:0] = $val1 - $val2;
            $prod[31:0] = $val1 * $val2;
            $quot[31:0] = $val1 / $val2;
            
         @2   
            $out [31:0] = $reset ? 32'b0 :
                          ($op[1:0] == 2'b00) ? $sum :
                          ($op[1:0] == 2'b01) ? $diff :
                          ($op[1:0] == 2'b10) ? $prod :
                                                $quot ;
```
Here is the TL code and output Waveform
![Validity_calc](https://github.com/user-attachments/assets/834530fc-67d6-465a-9122-43ed0a00fcc5)
</details>
</details>
<details>
	<summary>Day 4</summary>
	<br>

 <details>
	 <summary>Fetch and Decode</summary>
	 <br>

  ## Fetch ##
  
In the fetch stage, the processor retrieves the instruction from memory at the address specified by the program counter. The program counter contains the address for the next instruction, which in our case is after 4 cycles, and the instruction memory stores the instructions to be executed. 
![Fetch_block](https://github.com/user-attachments/assets/43a24966-4b6e-4748-82e6-69a0b0b09796)

#### Logic ####
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $clk_man = *clk;
   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Program for MYTH Workshop to test RV32I
   // Add 1,2,3,...,9 (in that order).
   //
   // Registers:
   //  r1 (s0): In: 0, Out: final sum
   //  r2 (s1): 10
   //  r3 (s2): 1..10
   //  r4 (s3): Sum
   // 
   // External to function:
   m4_asm(ADD, r1, r0, r0)             // Initialize r1 (s0) to 0.
   // Function:
   m4_asm(ADD, r4, r1, r0)             // Initialize sum register s3 with 0x0
   m4_asm(ADDI, r2, r1, 1010)          // Store count of 10 in register s1.
   m4_asm(ADD, r3, r1, r0)             // Initialize intermediate sum register s2 with 0
   // Loop:
   m4_asm(ADD, r4, r3, r4)             // Incremental addition
   m4_asm(ADDI, r3, r3, 1)             // Increment intermediate register by 1
   m4_asm(BLT, r3, r2, 1111111111000)  // If s2 is less than s1, branch to label named <loop>
   m4_asm(ADD, r1, r4, r0)             // Store final result to register s0 so that it can be read by the main program
   
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |processor
      @0
         $reset_signal = *reset;
         $program_counter[31:0] = >>1$reset_signal ? 32'b0 : (>>1$program_counter + 32'd4);
         
      @1
         $instruction_memory_enable = !$reset_signal;
         $instruction_memory_address[M4_IMEM_INDEX_CNT-1:0] = $program_counter[M4_IMEM_INDEX_CNT+1:2];
         $instruction[31:0] = $instruction_memory_data[31:0]; 
   
   // Assert these to end simulation (before Makerchip cycle limit).
   *simulation_passed = *cyc_cnt > 40;
   *simulation_failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   |processor
      m4+imem(@1)    // Args: (read stage)
      //m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)

\SV
   endmodule
```
![Fetch](https://github.com/user-attachments/assets/078701ec-1e30-4c42-b9f0-ec127b3a52dd)

## Decode ##
To decode a specific instruction, the processor must be aware of the instruction's type and format. Accurate decoding is crucial to avoid errors and ensure proper operation. In RISC-V, there are six instruction types, each with its own format:

Register (R) Type: Instructions that operate on registers.
Immediate (I) Type: Instructions that include an immediate value.
Store (S) Type: Instructions that store data from a register to memory.
Branch (B) Type: Instructions that perform conditional branching based on a comparison.
Upper Immediate (U) Type: Instructions that handle immediate values used for upper 20 bits.
Jump (J) Type: Instructions that perform jumps to different locations in the code.
Proper decoding of each type ensures that the instruction is executed correctly according to its intended operation.
![Decode_block](https://github.com/user-attachments/assets/0042c257-782d-4173-89ef-2d115cf88d21)

#### Logic: ####
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $clk_man = *clk;
   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Program for MYTH Workshop to test RV32I
   // Add 1,2,3,...,9 (in that order).
   //
   // Registers:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): Count limit (10)
   //  r13 (a3): Loop counter (1..10)
   //  r14 (a4): Accumulated sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize loop counter register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment loop counter register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
         
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0]; 
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b0x100 ||
                       $instr[6:2] ==? 5'b01110;
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? { {20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? { $instr[31:12], 12'b0} :
                      $is_j_instr ? { {12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} : 32'b0;
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
         
         $rs1_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs1_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$funct3_valid
            $funct3[3:0] = $instr[14:12];
   
         $opcode[6:0] = $instr[6:0];
         
         $funct7_valid = $is_r_instr;
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
            
         $dec_bits[10:0] = {$funct7[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits == 11'b0_000_0110011;

   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   |cpu
      m4+imem(@1)    // Args: (read stage)
      //m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)

\SV
   endmodule
```
Here is the TL code and output wave form
![Decode](https://github.com/user-attachments/assets/1455c480-963e-4175-98e8-ccc5ba285354)
</details>
<details>
	<summary>Read and Write</summary>
	<br>

 
## Register File Read ##
Register reading in a CPU involves accessing the contents of specified registers to retrieve values needed for various operations. This process is crucial for instruction execution, as it provides the operands required for arithmetic, logic, and data manipulation tasks. Register reading typically involves decoding instructions to identify which registers to access and then using these registers' values in the CPU’s computation and control logic.
![File_read](https://github.com/user-attachments/assets/2398be2e-5146-4fc9-a899-33bc12bf329a)

#### Logic: ####
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $clk_man = *clk;
   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Program for MYTH Workshop to test RV32I
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
         
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0]; 
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b0x100 ||
                       $instr[6:2] ==? 5'b01110;
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? { {20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? { $instr[31:12], 12'b0} :
                      $is_j_instr ? { {12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} : 32'b0;
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
         
         $rs1_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $funct3[3:0] = $instr[14:12];
   
         $opcode[6:0] = $instr[6:0];
         
         $funct7_valid = $is_r_instr;
         ?$rs2_valid
            $funct7[6:0] = $instr[31:25];
            
         $dec_bits[10:0] = {$funct[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits == 11'b0_000_0110011;
         
         $rf_rd_en1 = !$rs1_valid;
         $rd_rd_en2 = !$rs2_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_index2[4:0] = $rs2;
         $rf_rd_data1[31:0] = $src1_value[31:0]; 
         $rf_rd_data2[31:0] = $src2_value[31:0];
         
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
   
\SV
   endmodule
```
![read](https://github.com/user-attachments/assets/54349c5c-d9f6-47f4-9ad2-d78b3b023a78)
## Register File Write ##
Register writing involves updating the contents of specified registers with new values produced by computations or operations. This process is essential for storing results of arithmetic or logical operations, setting up data for future instructions, or modifying control information. Register writing is typically managed by decoding instructions to determine the target registers and then transferring the computed values into those registers as part of the CPU’s execution cycle.
![File_write](https://github.com/user-attachments/assets/4b5446ff-45f9-48b9-932e-734c894a8d75)

#### Logic: ####
```
\m4_TLV_version 1d: tl-x.org
\SV
   // This code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/stevehoover/RISC-V_MYTH_Workshop/c1719d5b338896577b79ee76c2f443ca2a76e14f/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $clk_man = *clk;
   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Program for MYTH Workshop to test RV32I
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   
   // Optional:
   // m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         $pc[31:0] = >>1$reset ? 32'b0 : (>>1$pc + 32'd4);
         
      @1
         $imem_rd_en = !$reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         $instr[31:0] = $imem_rd_data[31:0]; 
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] ==? 5'b11001 ||
                       $instr[6:2] ==? 5'b11100;
         $is_r_instr = $instr[6:2] ==? 5'b01011 ||
                       $instr[6:2] ==? 5'b0x100 ||
                       $instr[6:2] ==? 5'b01110;
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         $is_b_instr = $instr[6:2] ==? 5'b11000;
         $is_j_instr = $instr[6:2] ==? 5'b11011;
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}}, $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}}, $instr[30:25], $instr[11:7]} :
                      $is_b_instr ? { {20{$instr[31]}}, $instr[7], $instr[30:25], $instr[11:8], 1'b0} :
                      $is_u_instr ? { $instr[31:12], 12'b0} :
                      $is_j_instr ? { {12{$instr[31]}}, $instr[19:12], $instr[20], $instr[30:21], 1'b0} : 32'b0;
         
         $rs2_valid = $is_r_instr || $is_s_instr || $is_b_instr;
         ?$rs2_valid
            $rs2[4:0] = $instr[24:20];
         
         $rs1_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $rs1[4:0] = $instr[19:15];
         
         $funct3_valid = $is_r_instr || $is_s_instr || $is_b_instr || $is_i_instr;
         ?$rs2_valid
            $funct3[3:0] = $instr[14:12];
   
         $opcode[6:0] = $instr[6:0];
         
         $funct7_valid = $is_r_instr;
         ?$rs2_valid
            $funct7[6:0] = $instr[31:25];
            
         $rd_valid = $is_r_instr || $is_u_instr || $is_j_instr || $is_i_instr;
         ?$rd_valid
            $rd[4:0] = $instr[11:7]; 
            
         $dec_bits[10:0] = {$funct[5], $funct3, $opcode};
         $is_beq = $dec_bits ==? 11'bx_000_1100011;
         $is_bne = $dec_bits ==? 11'bx_001_1100011;
         $is_blt = $dec_bits ==? 11'bx_100_1100011;
         $is_bge = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu = $dec_bits ==? 11'bx_111_1100011;
         $is_addi = $dec_bits ==? 11'bx_000_0010011;
         $is_add = $dec_bits == 11'b0_000_0110011;
         
         `BOGUS_USE($is_beq $is_bne $is_blt $is_bge $is_bltu $is_bgeu $is_addi $is_add)
         
         $rf_rd_en1 = $rs1_valid;
         $rd_rd_en2 = $rs2_valid;
         $rf_rd_index1[4:0] = $rs1;
         $rf_rd_index2[4:0] = $rs2;
         $rf_rd_data1[31:0] = $src1_value[31:0]; 
         $rf_rd_data2[31:0] = $src2_value[31:0];
         
         $result[31:0] = $is_addi ? $src1_value + $imm :
                         $is_add ? $src1_value + $src2_value :
                         32'bx;
         
         $rf_wr_en = ($rd_valid || $rd !== 5'b0);  
         $rf_wr_index[4:0] = $rd;
         $rf_wr_data[31:0] = $result;
         
   // Assert these to end simulation (before Makerchip cycle limit).
   *passed = *cyc_cnt > 40;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@1, @1)  // Args: (read stage, write stage) - if equal, no register bypass is required
      //m4+dmem(@4)    // Args: (read/write stage)
 
\SV
   endmodule
```
Here is the TL code and output waveform
![write](https://github.com/user-attachments/assets/be6f4b38-1745-43a3-8d6b-4c78b9e79f0a)
 </details>
</details>
<details>
	<summary>Day 5</summary>
	<br>

This is a CPU simulation setup that executes a program to compute the sum of integers from 1 to 9. The main focus is on how the processor executes instructions and manages control signals to perform operations.

### Key Components and Functionality
#### Instruction Memory and Fetch:

##### PC (Program Counter):
Determines the address of the instruction to be fetched.
##### Instruction Fetch:
The instruction memory (imem) is accessed using the PC address to get the instruction.
##### Instruction Decoding: 
The fetched instruction is decoded to determine its type and fields (e.g., opcode, funct3, funct7).
##### Immediate Value Extraction: 
Extracts and sign-extends immediate values from the instruction based on the type (I-type, S-type, B-type, U-type, J-type).
#### Control Signals:

##### Branch Instructions:
Determines if the branch should be taken based on the comparison of register values.
##### Jump Instructions:
Computes the target address for jumps and sets the new PC value accordingly.
##### Arithmetic Instructions: 
Performs arithmetic operations like addition and immediate addition.
#### Execution:

##### Memory Operations:
Handles read and write operations for the data memory.
##### Register File Operations: 
Reads from and writes to registers based on the decoded instruction and control signals.
#### Program Execution:

##### Sum Calculation:
Adds integers from 1 to 9. The sum is stored in r10, and the final result is written back to memory.
##### Program Termination:
Ends the simulation by jumping to itself (infinite loop).
#### Detailed Steps
##### Initialization:

r10 (a0) is initialized to 0, which will hold the final sum.
Other registers are initialized for use in the program.
Program Execution:

The program computes the sum of integers from 1 to 9 using a loop.
##### Loop Logic: 
Adds the value of the loop counter to the sum, increments the counter, and checks if the loop should continue.
#### Memory and Register Operations:

##### Load/Store Operations:
Results are stored in and loaded from memory.
##### Arithmetic Operations:
Performed using the decoded instruction and immediate values.
End of Simulation:

The simulation ends, and the final result is verified.
Control Signals and Execution Flow
Branch and Jump Instructions: Control the flow of execution based on comparison and immediate values.
Arithmetic Operations: Manage the addition of integers and store results.
This simulation helps in understanding how a RISC-V CPU executes a given set of instructions and handles different types of operations.
![image](https://github.com/user-attachments/assets/3a2c050c-bbf2-4db9-a72b-13be07b119d8)

#### Code ####
```
\m4_TLV_version 1d: tl-x.org
\SV
   // Template code can be found in: https://github.com/stevehoover/RISC-V_MYTH_Workshop
   
   m4_include_lib(['https://raw.githubusercontent.com/BalaDhinesh/RISC-V_MYTH_Workshop/master/tlv_lib/risc-v_shell_lib.tlv'])

\SV
   m4_makerchip_module   // (Expanded in Nav-TLV pane.)
\TLV
   $clk_man = *clk;
   // /====================\
   // | Sum 1 to 9 Program |
   // \====================/
   //
   // Add 1,2,3,...,9 (in that order).
   //
   // Regs:
   //  r10 (a0): In: 0, Out: final sum
   //  r12 (a2): 10
   //  r13 (a3): 1..10
   //  r14 (a4): Sum
   // 
   // External to function:
   m4_asm(ADD, r10, r0, r0)             // Initialize r10 (a0) to 0.
   // Function:
   m4_asm(ADD, r14, r10, r0)            // Initialize sum register a4 with 0x0
   m4_asm(ADDI, r12, r10, 1010)         // Store count of 10 in register a2.
   m4_asm(ADD, r13, r10, r0)            // Initialize intermediate sum register a3 with 0
   // Loop:
   m4_asm(ADD, r14, r13, r14)           // Incremental addition
   m4_asm(ADDI, r13, r13, 1)            // Increment intermediate register by 1
   m4_asm(BLT, r13, r12, 1111111111000) // If a3 is less than a2, branch to label named <loop>
   m4_asm(ADD, r10, r14, r0)            // Store final result to register a0 so that it can be read by main program
   m4_asm(SW, r0, r10, 10000)           // Store r10 result in dmem
   m4_asm(LW, r17, r0, 10000)           // Load contents of dmem to r17
   m4_asm(JAL, r7, 00000000000000000000) // Done. Jump to itself (infinite loop). (Up to 20-bit signed immediate plus implicit 0 bit (unlike JALR) provides byte address; last immediate bit should also be 0)
   m4_define_hier(['M4_IMEM'], M4_NUM_INSTRS)

   |cpu
      @0
         $reset = *reset;
         
         //PC fetch - branch, jumps and loads introduce 2 cycle bubbles in this pipeline
         $pc[31:0] = >>1$reset ? '0 : (>>3$valid_taken_br ? >>3$br_tgt_pc :
                                       >>3$valid_load     ? >>3$inc_pc[31:0] :
                                       >>3$jal_valid      ? >>3$br_tgt_pc :
                                       >>3$jalr_valid     ? >>3$jalr_tgt_pc :
                                                     (>>1$inc_pc[31:0]));
         // Access instruction memory using PC
         $imem_rd_en = ~ $reset;
         $imem_rd_addr[M4_IMEM_INDEX_CNT-1:0] = $pc[M4_IMEM_INDEX_CNT+1:2];
         
         
      @1
         //Getting instruction from IMem
         $instr[31:0] = $imem_rd_data[31:0];
         
         //Increment PC
         $inc_pc[31:0] = $pc[31:0] + 32'h4;
         
         //Decoding I,R,S,U,B,J type of instructions based on opcode [6:0]
         //Only [6:2] is used here because this implementation is for RV64I which does not use [1:0]
         $is_i_instr = $instr[6:2] ==? 5'b0000x ||
                       $instr[6:2] ==? 5'b001x0 ||
                       $instr[6:2] == 5'b11001;
         
         $is_r_instr = $instr[6:2] == 5'b01011 ||
                       $instr[6:2] ==? 5'b011x0 ||
                       $instr[6:2] == 5'b10100;
         
         $is_s_instr = $instr[6:2] ==? 5'b0100x;
         
         $is_u_instr = $instr[6:2] ==? 5'b0x101;
         
         $is_b_instr = $instr[6:2] == 5'b11000;
         
         $is_j_instr = $instr[6:2] == 5'b11011;
         
         //Immediate value decode
         $imm[31:0] = $is_i_instr ? { {21{$instr[31]}} , $instr[30:20]} :
                      $is_s_instr ? { {21{$instr[31]}} , $instr[30:25] , $instr[11:8] , $instr[7]} :
                      $is_b_instr ? { {20{$instr[31]}} , $instr[7] , $instr[30:25] , $instr[11:8] , 1'b0} :
                      $is_u_instr ? { $instr[31] , $instr[30:12] , { 12{1'b0}} } :
                      $is_j_instr ? { {12{$instr[31]}} , $instr[19:12] , $instr[20] , $instr[30:21] , 1'b0} :
                      >>1$imm[31:0];
         
         //Generate valid signals for each instruction fields
         $rs1_or_funct3_valid    = $is_r_instr || $is_i_instr || $is_s_instr || $is_b_instr;
         $rs2_valid              = $is_r_instr || $is_s_instr || $is_b_instr;
         $rd_valid               = $is_r_instr || $is_i_instr || $is_u_instr || $is_j_instr;
         $funct7_valid           = $is_r_instr;
         
         //Decode other fields of instruction - source and destination registers, funct, opcode
         ?$rs1_or_funct3_valid
            $rs1[4:0]    = $instr[19:15];
            $funct3[2:0] = $instr[14:12];
         
         ?$rs2_valid
            $rs2[4:0]    = $instr[24:20];
         
         ?$rd_valid
            $rd[4:0]     = $instr[11:7];
         
         ?$funct7_valid
            $funct7[6:0] = $instr[31:25];
         
         $opcode[6:0] = $instr[6:0];
         
         //Decode instruction in subset of base instruction set based on RISC-V 32I
         $dec_bits[10:0] = {$funct7[5],$funct3,$opcode};
         
         //Branch instructions
         $is_beq   = $dec_bits ==? 11'bx_000_1100011;
         $is_bne   = $dec_bits ==? 11'bx_001_1100011;
         $is_blt   = $dec_bits ==? 11'bx_100_1100011;
         $is_bge   = $dec_bits ==? 11'bx_101_1100011;
         $is_bltu  = $dec_bits ==? 11'bx_110_1100011;
         $is_bgeu  = $dec_bits ==? 11'bx_111_1100011;
         
         //Jump instructions
         $is_auipc = $dec_bits ==? 11'bx_xxx_0010111;
         $is_jal   = $dec_bits ==? 11'bx_xxx_1101111;
         $is_jalr  = $dec_bits ==? 11'bx_000_1100111;
         
         //Arithmetic instructions
         $is_addi  = $dec_bits ==? 11'bx_000_0010011;
         $is_add   = $dec_bits ==  11'b0_000_0110011;
         $is_lui   = $dec_bits ==? 11'bx_xxx_0110111;
         $is_slti  = $dec_bits ==? 11'bx_010_0010011;
         $is_sltiu = $dec_bits ==? 11'bx_011_0010011;
         $is_xori  = $dec_bits ==? 11'bx_100_0010011;
         $is_ori   = $dec_bits ==? 11'bx_110_0010011;
         $is_andi  = $dec_bits ==? 11'bx_111_0010011;
         $is_slli  = $dec_bits ==? 11'b0_001_0010011;
         $is_srli  = $dec_bits ==? 11'b0_101_0010011;
         $is_srai  = $dec_bits ==? 11'b1_101_0010011;
         $is_sub   = $dec_bits ==? 11'b1_000_0110011;
         $is_sll   = $dec_bits ==? 11'b0_001_0110011;
         $is_slt   = $dec_bits ==? 11'b0_010_0110011;
         $is_sltu  = $dec_bits ==? 11'b0_011_0110011;
         $is_xor   = $dec_bits ==? 11'b0_100_0110011;
         $is_srl   = $dec_bits ==? 11'b0_101_0110011;
         $is_sra   = $dec_bits ==? 11'b1_101_0110011;
         $is_or    = $dec_bits ==? 11'b0_110_0110011;
         $is_and   = $dec_bits ==? 11'b0_111_0110011;
         
         //Store instructions
         $is_sb    = $dec_bits ==? 11'bx_000_0100011;
         $is_sh    = $dec_bits ==? 11'bx_001_0100011;
         $is_sw    = $dec_bits ==? 11'bx_010_0100011;
         
         //Load instructions - support only 4 byte load
         $is_load  = $dec_bits ==? 11'bx_xxx_0000011;
         
         $is_jump = $is_jal || $is_jalr;
         
      @2
         //Get Source register values from reg file
         $rf_rd_en1 = $rs1_or_funct3_valid;
         $rf_rd_en2 = $rs2_valid;
         
         $rf_rd_index1[4:0] = $rs1[4:0];
         $rf_rd_index2[4:0] = $rs2[4:0];
         
         //Register file bypass logic - data forwarding from ALU to resolve RAW dependence
         $src1_value[31:0] = $rs1_bypass ? >>1$result[31:0] : $rf_rd_data1[31:0];
         $src2_value[31:0] = $rs2_bypass ? >>1$result[31:0] : $rf_rd_data2[31:0];
         
         //Branch target PC computation for branches and JAL
         $br_tgt_pc[31:0] = $imm[31:0] + $pc[31:0];
         
         //RAW dependence check for ALU data forwarding
         //If previous instruction was writing to reg file, and current instruction is reading from same register
         $rs1_bypass = >>1$rf_wr_en && (>>1$rd == $rs1);
         $rs2_bypass = >>1$rf_wr_en && (>>1$rd == $rs2);
         
      @3
         //ALU
         $result[31:0] = $is_addi  ? $src1_value +  $imm :
                         $is_add   ? $src1_value +  $src2_value :
                         $is_andi  ? $src1_value &  $imm :
                         $is_ori   ? $src1_value |  $imm :
                         $is_xori  ? $src1_value ^  $imm :
                         $is_slli  ? $src1_value << $imm[5:0]:
                         $is_srli  ? $src1_value >> $imm[5:0]:
                         $is_and   ? $src1_value &  $src2_value:
                         $is_or    ? $src1_value |  $src2_value:
                         $is_xor   ? $src1_value ^  $src2_value:
                         $is_sub   ? $src1_value -  $src2_value:
                         $is_sll   ? $src1_value << $src2_value:
                         $is_srl   ? $src1_value >> $src2_value:
                         $is_sltu  ? $sltu_rslt[31:0]:
                         $is_sltiu ? $sltiu_rslt[31:0]:
                         $is_lui   ? {$imm[31:12], 12'b0}:
                         $is_auipc ? $pc + $imm:
                         $is_jal   ? $pc + 4:
                         $is_jalr  ? $pc + 4:
                         $is_srai  ? ({ {32{$src1_value[31]}} , $src1_value} >> $imm[4:0]) :
                         $is_slt   ? (($src1_value[31] == $src2_value[31]) ? $sltu_rslt : {31'b0, $src1_value[31]}):
                         $is_slti  ? (($src1_value[31] == $imm[31]) ? $sltiu_rslt : {31'b0, $src1_value[31]}) :
                         $is_sra   ? ({ {32{$src1_value[31]}}, $src1_value} >> $src2_value[4:0]) :
                         $is_load  ? $src1_value +  $imm :
                         $is_s_instr ? $src1_value + $imm :
                                    32'bx;
         
         $sltu_rslt[31:0]  = $src1_value <  $src2_value;
         $sltiu_rslt[31:0] = $src1_value <  $imm;
         
         //Jump instruction target PC computation
         $jalr_tgt_pc[31:0] = $imm[31:0] + $src1_value[31:0]; 
         
         //Branch resolution
         $taken_br = $is_beq ? ($src1_value == $src2_value) :
                     $is_bne ? ($src1_value != $src2_value) :
                     $is_blt ? (($src1_value < $src2_value) ^ ($src1_value[31] != $src2_value[31])) :
                     $is_bge ? (($src1_value >= $src2_value) ^ ($src1_value[31] != $src2_value[31])) :
                     $is_bltu ? ($src1_value < $src2_value) :
                     $is_bgeu ? ($src1_value >= $src2_value) :
                     1'b0;
         
         //Current instruction is valid if one of the previous 2 instructions were not (taken_branch or load or jump)
         $valid = ~(>>1$valid_taken_br || >>2$valid_taken_br || >>1$is_load || >>2$is_load || >>2$jump_valid || >>1$jump_valid);
         
         //Current instruction is valid & is a taken branch
         $valid_taken_br = $valid && $taken_br;
         
         //Current instruction is valid & is a load
         $valid_load = $valid && $is_load;
         
         //Current instruction is valid & is jump
         $jump_valid = $valid && $is_jump;
         $jal_valid  = $valid && $is_jal;
         $jalr_valid = $valid && $is_jalr;
         
         //Destination register update - ALU result or load result depending on instruction
         $rf_wr_en = (($rd != '0) && $rd_valid && $valid) || >>2$valid_load;
         $rf_wr_index[4:0] = $valid ? $rd[4:0] : >>2$rd[4:0];
         $rf_wr_data[31:0] = $valid ? $result[31:0] : >>2$ld_data[31:0];
         
      @4
         //Data memory access for load, store
         $dmem_addr[3:0]     =  $result[5:2];
         $dmem_wr_en         =  $valid && $is_s_instr;
         $dmem_wr_data[31:0] =  $src2_value[31:0];
         $dmem_rd_en         =  $valid_load;
         
      
         //Write back data read from load instruction to register
         $ld_data[31:0]      =  $dmem_rd_data[31:0];
         
      
      

      // Note: Because of the magic we are using for visualisation, if visualisation is enabled below,
      //       be sure to avoid having unassigned signals (which you might be using for random inputs)
      //       other than those specifically expected in the labs. You'll get strange errors for these.

   
   // Assert these to end simulation (before Makerchip cycle limit).
   //Checks if sum of numbers from 1 to 9 is obtained in reg[17] and runs 10 cycles extra after this is met
   *passed = |cpu/xreg[17]>>10$value == (1+2+3+4+5+6+7+8+9);
   //Run for 200 cycles without any checks
   //*passed = *cyc_cnt > 200;
   *failed = 1'b0;
   
   // Macro instantiations for:
   //  o instruction memory
   //  o register file
   //  o data memory
   //  o CPU visualization
   |cpu
      m4+imem(@1)    // Args: (read stage)
      m4+rf(@2, @3)  // Args: (read stage, write stage) - if equal, no register bypass is required
      m4+dmem(@4)    // Args: (read/write stage)
   
   m4+cpu_viz(@4)    // For visualisation, argument should be at least equal to the last stage of CPU logic
                       // @4 would work for all labs
\SV
   endmodule
```
#### Diagram: ####
![day5_cir](https://github.com/user-attachments/assets/f2d2c65a-0ef0-4a29-9300-ac51c0ed302e)
#### Wave Forms ####
![risc-v](https://github.com/user-attachments/assets/8ef85cb5-8c49-4109-a0a7-14edfd8a7ca2)
output 
![output](https://github.com/user-attachments/assets/133e8997-a4cf-43ae-822b-b97223f5000a)

#### VIZ ####
![viz](https://github.com/user-attachments/assets/3cc02ff1-48cc-47ca-8a51-77d5cc961ded)

</details>
</details>
<details>
	<summary>ASIC Lab 6</summary>
	<br>

# Conversion of TL-Verilog to Verilog with Sandpiper: Simulation and Waveform Analysis

## Aim

This project demonstrates the comparison of RISC-V pre-synthesis simulation outputs using Icarus Verilog, GTKWave, and Makerchip. The RISC-V processor is initially designed using TL-Verilog in the Makerchip IDE. To implement the design on an FPGA, it is first converted to Verilog using the Sandpiper-SaaS compiler. Pre-synthesis simulations are then performed using the Icarus Verilog and GTKWave tools.

## Prerequisites

Before beginning, ensure that you have the following tools and libraries installed on your system:
- **Python**: Version 3
- **Python3-venv**: For creating isolated Python environments
- **pip**: Python package installer
- **Git**: Version control system
- **Icarus Verilog**: Open-source Verilog simulator
- **GTKWave**: Waveform viewer
- **Docker**: For containerization support
- **Sandpiper-SaaS**: TL-Verilog to Verilog compiler

## Step-by-Step Process

Follow these steps to set up and run the RISC-V pre-synthesis simulation:

1. **Install Required Packages**:

First, install the necessary packages and tools on your system. Run the following commands:

 ```bash
    sudo apt update
    sudo apt install -y make python python3 python3-pip git iverilog gtkwave docker.io
    sudo chmod 666 /var/run/docker.sock
    sudo apt-get install python3-venv
 ```

2. **Set Up Python Environment**:

Set up a Python virtual environment and install the required Python packages:

 ```bash
    cd ~
    python3 -m venv .venv
    source ~/.venv/bin/activate
    pip install pyyaml click sandpiper-saas
 ```

3. **Clone the Repository**:                                                                                                                                      

Clone the VSDBabySoC repository into your home directory:

```bash
    git clone https://github.com/manili/VSDBabySoC.git
 ```

4. **Replace TL-Verilog File**:                                                                                                                              

Replace the existing `.tlv` file in the `VSDBabySoC/src/module` directory with your custom RISC-V `.tlv` file. This file should contain the RISC-V processor design that you want to simulate.

5. **Navigate to the Project Directory**:

 Change your working directory to the cloned repository:

```bash
    cd VSDBabySoC
 ```

6. **Convert TL-Verilog to Verilog**:

Use the Sandpiper-SaaS compiler to convert your TL-Verilog design into Verilog:

 ```bash
    sandpiper-saas -i ./src/module/*.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir ./src/module/
  ```

7. **Create Pre-Synthesis Simulation File**:

Run the following command to create the `pre_synth_sim.vcd` file, which is necessary for simulation:

 ```bash
    make pre_synth_sim
 ```

8. **Compile and Simulate RISC-V Design**:

Compile the Verilog files and run the simulation using Icarus Verilog:

```bash
    iverilog -o output/pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module
 ```

9. **Run the Simulation Output**:

Navigate to the output directory and execute the simulation output file to generate the waveform:

 ```bash
    cd output
    ./pre_synth_sim.out
 ```

10. **View Simulation Results with GTKWave**:

 Use GTKWave to view the waveform of the simulation results:

```bash
    gtkwave pre_synth_sim.vcd
```

11. **Analyze the Waveforms**:

 Use GTKWave to analyze the output waveforms. Compare different runs to verify the functionality and performance of your RISC-V processor design.
 
###  GTKWave Output Waveform

![verilog](https://github.com/user-attachments/assets/6d55c95a-8b6a-4d95-9525-1ccf3eb38f6d)


### Comparison of Output Waveforms

![output](https://github.com/user-attachments/assets/4906dfef-0bef-4924-96e1-000252e1a699)


## Conclusion
The waveform outputs from GTKWave and Makerchip matched perfectly, validating the RISC-V processor design's accuracy and consistency. This alignment confirms that the design of RISC-V core processor is robust.


</details>
<details>
	<summary>ASIC Lab 7</summary>
	<br>

 # RISC-V Pre-Synthesis Analog Simulation Analysis

## Objective

Analyze RISC-V Pre-Synthesis Analog Simulation Outputs Using Iverilog and GTKWave.

## Sub-Task 1: Tools Installation

### Install Yosys

Yosys is a framework for RTL synthesis. Follow these steps to install it:

1. **Clone the Yosys Repository**
    ```bash
    git clone https://github.com/YosysHQ/yosys.git
    cd yosys
    ```

2. **Ensure `make` is Installed**
    ```bash
    sudo apt install make
    ```

3. **Install Required Dependencies**
    ```bash
    sudo apt-get install build-essential clang bison flex \
        libreadline-dev gawk tcl-dev libffi-dev git \
        graphviz xdot pkg-config python3 libboost-system-dev \
        libboost-python-dev libboost-filesystem-dev zlib1g-dev
    ```

4. **Compile Yosys**
    ```bash
    make config-gcc
    make
    sudo make install
    ```

5. **Verify Yosys Installation**
    ```bash
    yosys
    ```
![Screenshot from 2024-09-02 18-01-19](https://github.com/user-attachments/assets/1acfbcd9-25bc-4d67-8cea-d1187e18c151)

### Install IVerilog

IVerilog is a Verilog simulation and synthesis tool. Follow these steps to install it:

1. **Install IVerilog**
    ```bash
    sudo apt-get install iverilog
    ```

2. **Verify IVerilog Installation**
    ```bash
    iverilog -v
    ```
![Screenshot from 2024-09-02 18-03-11](https://github.com/user-attachments/assets/ed251a03-ce67-4849-ae5a-c68c044cde27)

### Install GTKWave

GTKWave is a waveform viewer used for debugging digital circuits. Follow these steps to install it:

1. **Update and Install GTKWave**
    ```bash
    sudo apt update
    sudo apt install gtkwave
    ```


2. **Verify GTKWave Installation**
    ```bash
    gtkwave
    ```
![Screenshot from 2024-09-02 18-04-34](https://github.com/user-attachments/assets/7cfcba2c-4eae-4dba-9c16-c8928e4573b5)

### Install OpenSTA

OpenSTA is used for static timing analysis. Follow these steps to install it:

1. **Clone OpenSTA Repository**
    ```bash
    git clone https://github.com/The-OpenROAD-Project/OpenSTA.git
    cd OpenSTA
    mkdir build
    cd build
    ```

2. **Build OpenSTA**
    ```bash
    cmake ..
    make
    sudo make install
    ```

3. **Verify OpenSTA Installation**
    ```bash
    sta -v
![Screenshot from 2024-09-02 19-07-52](https://github.com/user-attachments/assets/ca70a5be-f476-4419-a9fc-7cf974d44906)


## Sub-Task 2: BabySoC Simulation

VSDBabySoC is a small yet powerful RISC-V-based SoC designed to test open-source IP cores and calibrate the analog components. The main components include a RVMYTH microprocessor, an 8x-PLL for stable clock generation, and a 10-bit DAC for analog communication.

### Phase-Locked Loop (PLL)

A Phase-Locked Loop (PLL) is an electronic circuit that synchronizes an output signal's phase and frequency with a reference signal. It consists of three main components:

- **Phase Detector:** Compares the phase of the reference signal with the output signal and generates an error signal based on the difference.
- **Loop Filter:** Processes the error signal to smooth it out, reducing noise and improving stability.
- **Voltage-Controlled Oscillator (VCO):** Adjusts its output frequency based on the filtered error signal to minimize the phase difference.

PLLs are widely used in applications such as clock generation, frequency synthesis, and data recovery in communication systems.

### Digital-to-Analog Converter (DAC)

A Digital-to-Analog Converter (DAC) is an electronic device that converts digital signals (typically binary) into analog signals (such as voltage or current). This conversion is crucial in systems where digital data needs to be interpreted by analog devices or for output to be perceived by humans, like in audio and video equipment.

DACs are commonly used in applications like audio playback, video display, and signal processing.

### Navigate to VSDBabySoC Directory

1. **Navigate to VSDBabySoC Directory**
    ```bash
    cd VSDBabySoC
    ```

2. **Compile Verilog Files**
    ```bash
    iverilog -o ./pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module/
    ```

3. **Run the Simulation**
    ```bash
    ./pre_synth_sim.out
    ```

4. **View the Waveform in GTKWave**
    ```bash
    gtkwave pre_synth_sim.vcd
    ```

5. **Observed Results**
![Screenshot from 2024-09-02 16-43-37](https://github.com/user-attachments/assets/31b62db0-089f-4453-b97b-e84f7a8c5102)
![Screenshot from 2024-09-02 16-45-24](https://github.com/user-attachments/assets/d0b8db91-9a58-43e1-9e51-ec903b23f9b0)

    The simulation output will display the results, including:
    
    - `CLK`: The output clock signal from the PLL module.
    - `clk_Man`: The clock used by the RISC-V CPU for operations.
    - `reset`: The reset signal for the RISC-V CPU.
    - `REF`: The input clock reference signal to the PLL module.
    - `OUT`: The DAC output signal.


</details>
<details>
	<summary>ASIC Lab 8</summary>
	<br>

# RTL Design Using Verilog with SKY130 Technology

This documentation provides a detailed walkthrough of the RTL design process using Verilog, simulated with iVerilog and synthesized with Yosys, all within the context of SKY130 technology. It covers cloning the necessary repositories, running simulations with iVerilog, waveform analysis using GTKWave, and logic synthesis using Yosys.


<details>
<summary> Day-1</summary>
<br>
	
### Overview

This session introduces the flow of simulating a Verilog-based design using the iVerilog tool and visualizing the results with GTKWave. A simple 2:1 multiplexer is used as the example for this task.

<details>
<summary>Lab 1: Repository Cloning</summary>
<br>
	
#### Objective:
To begin working with Verilog files, the first step is to clone the required GitHub repository that contains the Verilog examples and files for simulation.

#### Procedure:

Run the following commands to set up your environment:

1. **Switch to root user**:
   ```bash
   sudo -i
   ```

2. **Install Git**:
   ```bash
   sudo apt-get install git
   ```

3. **Navigate to the home directory and create a working folder**:
   ```bash
   ls
   cd /home
   mkdir VLSI
   cd VLSI
   ```

4. **Clone the repository containing Verilog examples**:
   ```bash
   git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
   cd sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ls
   ```

At this point, you should have successfully cloned the repository and located the Verilog files necessary for the labs.

_Screenshot of the terminal window:_
![Screenshot from 2024-10-21 12-55-00](https://github.com/user-attachments/assets/73460891-84f7-4e82-b07f-2f01c3abd59e)



</details>

<details>
<summary>Lab 2: Introduction to iVerilog and GTKWave</summary>
<br>
	
#### Objective:
This lab focuses on implementing and simulating a basic 2:1 multiplexer using the iVerilog simulator and analyzing the waveform with GTKWave.

#### Steps:

1. **Open the Verilog code and its testbench**:
   Use the following command to view the 2:1 multiplexer Verilog file (`good_mux.v`) and the associated testbench file (`tb_good_mux.v`) in a text editor.
   ```bash
   gvim tb_good_mux.v -o good_mux.v
   ```

2. **Simulate the design**:
   Compile the Verilog files using iVerilog:
   ```bash
   iverilog good_mux.v tb_good_mux.v
   ```

3. **Run the compiled output**:
   ```bash
   ./a.out
   ```

4. **View the waveform in GTKWave**:
   The simulation will generate a `.vcd` file (Value Change Dump) which can be viewed in GTKWave.
   ```bash
   gtkwave tb_good_mux.vcd
   ```

_Screenshots of the terminal window and the GTKWave waveform:_

![Screenshot from 2024-10-21 12-07-26](https://github.com/user-attachments/assets/59c0a857-80bf-404d-b60a-c219bfe48004)


</details>

<details>
<summary>Lab 3: Synthesis of a 2:1 Multiplexer Using Yosys</summary>
<br>
	
#### Objective:
In this lab, we will perform logic synthesis of the 2:1 multiplexer designed earlier using **Yosys**, an open-source synthesis tool. The synthesized output will be a gate-level netlist, which can then be used for downstream steps such as placement and routing.


#### About Yosys:

**Yosys** is a widely-used open-source synthesis tool that converts Verilog RTL (Register Transfer Level) code into a gate-level netlist. The netlist represents the design in terms of logic gates, which can be implemented in physical hardware. Yosys applies various optimization techniques to reduce redundant logic, improve timing, and map the design to standard cells from a given technology library, such as SKY130.

The synthesis process in Yosys generally involves:
- **Reading the Verilog Design**: Yosys reads the RTL description of the design.
- **Optimization**: It optimizes the logic by removing redundant gates and simplifying the structure.
- **Mapping**: Yosys maps the optimized design to the gates defined in a technology-specific library (SKY130 in this case).
- **Generating Netlist**: Finally, it produces a gate-level netlist, a structural representation of the design in terms of logic gates and their interconnections.

Yosys is essential for transforming high-level RTL designs into gate-level hardware descriptions ready for fabrication. In this lab, we will use Yosys to synthesize the 2:1 multiplexer design.

---

#### Steps for Yosys Synthesis:

1. **Invoke Yosys**:
   Start the Yosys interactive shell with the command:
   ```bash
   yosys
   ```

2. **Load the SKY130 Standard Library**:
   Yosys requires a technology library to map the Verilog design to real gates. Load the SKY130 standard library using the following command:
   ```bash
   read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

3. **Read the Verilog Design**:
   Import the 2:1 multiplexer Verilog file into Yosys for synthesis:
   ```bash
   read_verilog good_mux.v
   ```

4. **Synthesize the Top-Level Module**:
   Instruct Yosys to synthesize the top-level module (`good_mux`):
   ```bash
   synth -top good_mux
   ```
   During this step, Yosys will optimize the design by minimizing logic redundancy, reordering gates, and potentially merging equivalent components.

5. **Map the Design to the Standard Library**:
   Yosys will then map the optimized RTL design to the gates defined in the loaded SKY130 library:
   ```bash
   abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```
   The ABC tool within Yosys handles this mapping process, ensuring the design conforms to the available cells in the standard library.

6. **Visualize the Generated Logic**:
   To view the synthesized design's gate-level schematic, use the following command:
   ```bash
   show
   ```
   This command opens an interactive viewer showing the interconnected gates, making it easier to understand the generated hardware logic.

7. **Save the Netlist**:
   After synthesis, save the gate-level netlist to a Verilog file:
   ```bash
   write_verilog -noattr good_mux_netlist.v
   ```
   You can open and inspect this netlist to see how the RTL design was transformed into gates:
   ```bash
   !gvim good_mux_netlist.v
   ```

_Screenshots of the Yosys flow and the generated logic diagram_:

![Screenshot from 2024-10-21 12-10-16](https://github.com/user-attachments/assets/6e8d5a5c-ff99-4270-96de-f1a861a4f8cc)
![Screenshot from 2024-10-21 12-11-29](https://github.com/user-attachments/assets/6ec7152f-0999-476a-b1bc-576ee0e0a1ab)
![Screenshot from 2024-10-21 12-21-24](https://github.com/user-attachments/assets/3eb4a73b-1784-4b8d-96c4-dc09493669e0)


</details>


</details>
<details>
<summary> Day-2</summary>
<br>
<details>
<summary>Lab 1: Introduction and Walkthrough to '.lib' File</summary>
<br>
	
#### Objective:
In this lab, we will explore the `.lib` file format, which contains a collection of standard cells, including details about their characteristics, such as delay, power, and area. We will specifically examine the **SKY130** standard cell library used in the RTL design process.


#### What is a '.lib' file?

A `.lib` file (also known as a Liberty file) is a technology-specific library that contains the characterization of various standard cells for a particular process node (such as 130nm for SKY130). The file includes details such as the process technology, environmental conditions (voltage, temperature), and timing/power characteristics of the cells.

The `.lib` file provides essential information for synthesis, placement, and routing tools to accurately map RTL designs into gate-level netlists.


<details>
<summary>Step 1: Viewing the '.lib' File</summary>

#### Procedure:

1. **Switch to the root user**:
   ```bash
   sudo -i
   ```

2. **Navigate to the directory containing the library**:
   ```bash
   cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/lib
   ```

3. **Open the Liberty file**:
   The `.lib` file you will explore is `sky130_fd_sc_hd__tt_025C_1v80.lib`. Open it using the `gvim` editor:
   ```bash
   gvim sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

4. **Disable syntax highlighting (optional)**:
   To turn off syntax highlighting for a clearer view of the contents, press:
   ```bash
   Shift + : syn off
   ```

At this point, you can begin analyzing the contents of the `.lib` file.
_Screenshots of terminal outputs and further walkthroughs of `.lib` contents:_
![Screenshot from 2024-10-21 14-28-23](https://github.com/user-attachments/assets/8e5b8a21-1b52-4c19-b61c-e8dfa33a106b)


</details>


<details>
<summary>Step 2: Understanding the Process Information</summary>

In the Liberty file, the process information is provided at the beginning of the file. Here’s what some of the key parameters indicate:

1. **Process Technology**:
   - The `.lib` file specifies that this technology is **CMOS** and it pertains to a 130nm process node:
     ```bash
     technology("cmos").
     ```

2. **Delay Model**:
   - The delay model used here is **table lookup**, which means the delay for each cell is characterized using lookup tables:
     ```bash
     delay_model : "table_lookup".
     ```

3. **Bus Naming Style**:
   - Defines how buses are named in the library:
     ```bash
     bus_naming_style : "%s[%d]".
     ```

4. **Units of Measurement**:
   - The `.lib` file defines various units, which include:
     ```bash
     time_unit : "1ns".
     voltage_unit : "1V".
     leakage_power_unit : "1nW".
     current_unit : "1mA".
     pulling_resistance_unit : "1kohm".
     capacitive_load_unit(1.0000000000, "pf").
     ```

This information tells you how the parameters are expressed within the Liberty file, including the units for time, voltage, leakage power, and capacitance.

</details>

<details>
<summary>Step 3: Cell Characteristics and Constraints</summary>

The `.lib` file contains detailed characteristics for each standard cell in the library. These include:

1. **Leakage Power**:
   - Specifies how much power is consumed by the cell in its idle state.

2. **Power Consumption**:
   - Describes the dynamic power consumed by the cell during switching.

3. **Area**:
   - The physical area that the cell occupies on the silicon.

4. **Input Capacitance and Delay**:
   - Defines the input capacitance and the delay introduced by the cell for different input combinations. 

Let’s explore the characteristics of a simple **2-input AND gate**:
![Screenshot from 2024-10-21 14-29-08](https://github.com/user-attachments/assets/0f3b0e2b-cca9-47ad-8800-cc9922cc557e)

- The `.lib` file includes detailed specifications for cells such as this AND gate, outlining its behavior under different input and output conditions.

</details>

---


</details>

<details>
<summary>Lab 2: Hierarchical Synthesis vs Flat Synthesis and Various D-Flip-Flops</summary>
<br>
	
#### Objective:
This lab aims to compare hierarchical synthesis and flat synthesis, as well as explore various coding styles for D-Flip-Flops, including their simulation and synthesis using Yosys.



<details>
<summary>Hierarchical Synthesis</summary>
<br>
	
#### Command Steps:

1. **Navigate to the required directory**:
   ```bash
   cd ~
   cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

2. **Start Yosys**:
   ```bash
   yosys
   ```

3. **Read the library**:
   ```bash
   read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

4. **Read the design Verilog files**:
   ```bash
   read_verilog multiple_modules.v
   ```

5. **Synthesize the Design**:
   ```bash
   synth -top multiple_modules
   ```

   When executing the `synth -top multiple_modules` command, a hierarchical synthesis is performed, preserving the hierarchy between modules.
![Screenshot from 2024-10-21 14-41-15](https://github.com/user-attachments/assets/f630517a-98d8-4bce-8f5a-420e2d94fda2)

6. **Generate the Netlist**:
   ```bash
   abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

7. **Create a Graphical Representation of Logic for Multiple Modules**:
   ```bash
   show multiple_modules
   ```
![Screenshot from 2024-10-21 14-40-26](https://github.com/user-attachments/assets/b8e91f7d-a1c5-47bb-97c6-d7dd7a5a73dc)

8. **Writing the netlist and viewing**:
   ```bash
   write_verilog -noattr multiple_modules_hier.v
   !vim multiple_modules_hier.v
   ```
![image](https://github.com/user-attachments/assets/15d96283-2099-45fb-8bf3-ae55292ae148)

9. **Flattening**:
   To merge all hierarchical modules into a single module, use:
   ```bash
   flatten
   ```

10. **Write and view the flattened netlist**:
    ```bash
    write_verilog -noattr multiple_modules_flat.v
    !vim multiple_modules_flat.v
    ```
![Screenshot from 2024-10-21 14-47-05](https://github.com/user-attachments/assets/ce1d76d6-1b3b-479e-a3b6-64d75693192f)
![Screenshot from 2024-10-21 14-46-44](https://github.com/user-attachments/assets/a2c2eed0-08ea-4e3e-8f3d-afcfd017f29f)

11. **Create a Graphical Representation of the Flattened Design**:
    ```bash
    show
    ```
![Screenshot from 2024-10-21 14-49-33](https://github.com/user-attachments/assets/d05d5e49-b09c-413b-a57f-f531cf03f04f)

</details>

---

<details>
<summary>Various D Flip-Flop Coding Styles</summary>
<br>
	
In this section, we will simulate different types of D Flip-Flops, including:

1. **Asynchronous Reset**
2. **Asynchronous Set**
3. **Synchronous Reset**

---

<details>
<summary>1. Asynchronous Reset</summary>

#### Verilog Code:
```verilog
module dff_asyncres(input clk, input async_reset, input d, output reg q);
    always@(posedge clk, posedge async_reset)
    begin
        if(async_reset)
            q <= 1'b0;
        else
            q <= d;
    end
endmodule
```

#### Testbench Code:
```verilog
module tb_dff_asyncres; 
    reg clk, async_reset, d;
    wire q;
    dff_asyncres uut (.clk(clk), .async_reset(async_reset), .d(d), .q(q));

    initial begin
        $dumpfile("tb_dff_asyncres.vcd");
        $dumpvars(0, tb_dff_asyncres);
        // Initialize Inputs
        clk = 0;
        async_reset = 1;
        d = 0;
        #3000 $finish;
    end

    always #10 clk = ~clk;
    always #23 d = ~d;
    always #547 async_reset = ~async_reset; 
endmodule
```

#### Command Steps:
1. **Navigate to the required directory**:
   ```bash
   sudo -i
   cd ~
   cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

2. **Compile and simulate**:
   ```bash
   iverilog dff_asyncres.v tb_dff_asyncres.v
   ```

3. **Run the simulation**:
   ```bash
   ./a.out
   gtkwave tb_dff_asyncres.vcd
   ```
![Screenshot from 2024-10-21 14-55-43](https://github.com/user-attachments/assets/3e38c9e8-9a0f-4d7b-83e6-249e3b8a24ac)

_Observation: The Q output changes to zero when the asynchronous reset is set high, independent of the clock edge._

</details>


<details>
<summary>2. Asynchronous Set</summary>
<br>
	
#### Verilog Code:
```verilog
module dff_async_set(input clk, input async_set, input d, output reg q);
    always@(posedge clk, posedge async_set)
    begin
        if(async_set)
            q <= 1'b1;
        else
            q <= d;
    end
endmodule
```

#### Testbench Code:
```verilog
module tb_dff_async_set; 
    reg clk, async_set, d;
    wire q;
    dff_async_set uut (.clk(clk), .async_set(async_set), .d(d), .q(q));

    initial begin
        $dumpfile("tb_dff_async_set.vcd");
        $dumpvars(0, tb_dff_async_set);
        // Initialize Inputs
        clk = 0;
        async_set = 1;
        d = 0;
        #3000 $finish;
    end

    always #10 clk = ~clk;
    always #23 d = ~d;
    always #547 async_set = ~async_set; 
endmodule
```

#### Command Steps:
1. **Navigate to the required directory**:
   ```bash
   sudo -i
   cd ~
   cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

2. **Compile and simulate**:
   ```bash
   iverilog dff_async_set.v tb_dff_async_set.v
   ```

3. **Run the simulation**:
   ```bash
   ./a.out
   gtkwave tb_dff_async_set.vcd
   ```
![Screenshot from 2024-10-21 14-59-51](https://github.com/user-attachments/assets/8171af57-6ad3-4cdf-8b8c-8e53c8c90fc3)

_Observation: The Q output changes to one when the asynchronous set is set high, independent of the clock edge._

</details>


<details>
<summary>3. Synchronous Reset</summary>
<br>
	
#### Verilog Code:
```verilog
module dff_syncres(input clk, input sync_reset, input d, output reg q);
    always@(posedge clk)
    begin
        if(sync_reset)
            q <= 1'b0;
        else
            q <= d;
    end
endmodule
```

#### Testbench Code:
```verilog
module tb_dff_syncres; 
    reg clk, sync_reset, d;
    wire q;
    dff_syncres uut (.clk(clk), .sync_reset(sync_reset), .d(d), .q(q));

    initial begin
        $dumpfile("tb_dff_syncres.vcd");
        $dumpvars(0, tb_dff_syncres);
        // Initialize Inputs
        clk = 0;
        sync_reset = 1;
        d = 0;
        #3000 $finish;
    end

    always #10 clk = ~clk;
    always #23 d = ~d;
    always #547 sync_reset = ~sync_reset; 
endmodule
```

#### Command Steps:
1. **Navigate to the required directory**:
   ```bash
   sudo -i
   cd ~
   cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

2. **Compile and simulate**:
   ```bash
   iverilog dff_syncres.v tb_dff_syncres.v
   ```

3. **Run the simulation**:
   ```bash
   ./a.out
   gtkwave tb_dff_syncres.vcd
   ```
![Screenshot from 2024-10-21 15-04-01](https://github.com/user-attachments/assets/eaca1086-6b45-4d38-b40c-b0d85c64a1d9)

_Observation: The Q output changes to zero when the synchronous reset is set high, only at the positive clock edge._

</details>

---

#### Synthesis of Various D-Flip-Flops Using Yosys:
We will synthesize the previously mentioned types of D-Flip-Flops using Yosys.

---

<details>
<summary>1. Asynchronous Reset D Flip-Flop</summary>
<br>
	
#### Command Steps:
1. **Navigate to the required directory**:
   ```bash
   cd ~
   cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

2. **Start Yosys**:
   ```bash
   yosys
   ```

3. **Read the library**:
   ```bash
   read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

4. **Read the design Verilog file**:
   ```bash
   read_verilog dff_asyncres.v
   ```

5. **Synthesize the Design**:
   ```bash
   synth -top dff_asyncres
   ```

6. **Generate the Netlist**:
   ```bash
   dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

7. **Create a Graphical Representation**:
   ```bash
   show
   ```
![Screenshot from 2024-10-21 15-09-56](https://github.com/user-attachments/assets/16b084a2-6d91-41ec-832d-2291349dec4e)

</details>


<details>
<summary>2. Asynchronous Set D Flip-Flop</summary>
<br>
	
#### Command Steps:
1. **Navigate to the required directory**:
   ```bash
   cd ~
   cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

2. **Start Yosys**:
   ```bash
   yosys
   ```

3. **Read the library**:
   ```bash
   read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

4. **Read the design Verilog file**:
   ```bash
   read_verilog dff_async_set.v
   ```

5. **Synthesize the Design**:
   ```bash
   synth -top dff_async_set
   ```

6. **Generate the Netlist**:
   ```bash
   dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

7. **Create a Graphical Representation**:
   ```bash
   show
   ```
![Screenshot from 2024-10-21 15-13-48](https://github.com/user-attachments/assets/5621d194-1174-4854-96a0-79cae58bd21a)

</details>


<details>
<summary>3. Synchronous Reset D Flip-Flop</summary>
<br>
	
#### Command Steps:
1. **Navigate to the required directory**:
   ```bash
   cd ~
   cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

2. **Start Yosys**:
   ```bash
   yosys
   ```

3. **Read the library**:
   ```bash
   read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

4. **Read the design Verilog file**:
   ```bash
   read_verilog dff_syncres.v
   ```

5. **Synthesize the Design**:
   ```bash
   synth -top dff_syncres
   ```

6. **Generate the Netlist**:
   ```bash
   dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

7. **Create a Graphical Representation**:
   ```bash
   show
   ```
![Screenshot from 2024-10-21 15-16-27](https://github.com/user-attachments/assets/a33f27d1-bfb3-4750-9dbe-afcf747f3d81)

</details>

</details>
<details>
	<summary> MUL 2</summary>
	<br>
	
## Multiplication by 2

In this tutorial, we learn that specific multiplier hardware is not necessary for multiplying a number by 2. This operation can be easily achieved by concatenating the number with a zero in the least significant bit (LSB).

### Steps:
1. **yosys**
2. **read_liberty** -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. **read_verilog** mult_2.v
4. **synth** -top mul2
5. **abc** -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. **show**
7. **write_verilog** -noattr mul2_net.v
8. **!gvim** mul2_net.v

### Design:
```verilog
module mul2(input [2:0]a, output [3:0]y);
	assign y=a*2;
endmodule
```
![Screenshot from 2024-10-22 11-11-48](https://github.com/user-attachments/assets/583ef487-6aec-4e6f-91ce-75fb4da66177)
![Screenshot from 2024-10-22 11-10-53](https://github.com/user-attachments/assets/75f7f2c8-7659-4fda-8b71-60ca2a43a4df)
![Screenshot from 2024-10-22 11-11-42](https://github.com/user-attachments/assets/33ed86e8-6725-4040-bd42-b443665571a1)

</details>
<details>
	<summary>MUL 8</summary>
	<br>

## Multiplication by 8

In this tutorial, we discover that specific multiplier hardware is not needed for multiplying a number by 9. This operation can be easily accomplished by concatenating the number with itself.

### Steps:
1. **yosys**
2. **read_liberty** -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
3. **read_verilog** mult_8.v
4. **synth** -top mult8
5. **abc** -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
6. **show**
7. **write_verilog** -noattr mul8_net.v
8. **!gvim** mul8_net.v

### Design:
```verilog
module mul8(input [2:0]a, output [5:0]y);
	assign y=a*8;
endmodule
```
![Screenshot from 2024-10-22 11-17-29](https://github.com/user-attachments/assets/ca4b5618-fd30-4a91-be89-f0f82e8546b5)
![Screenshot from 2024-10-22 11-17-21](https://github.com/user-attachments/assets/a08c463f-bcef-44f5-afc9-5012b1085a28)
![Screenshot from 2024-10-22 11-18-03](https://github.com/user-attachments/assets/72760a20-5bfc-43f9-b53c-3bf6891b1c0e)

</details>
</details>


</details>

---
<details>
  <summary> Day-3</summary>
<br>
	
  <details>
    <summary> Lab 1: Optimization of Various Combinational Designs</summary>
	  <br>

## Lab Objective:

This lab focuses on optimizing several fundamental combinational circuits, which include:

 - 2-input AND gate
 - 2-input OR gate
 - 3-input AND gate
 - 2-input XNOR gate (using 3-input Boolean logic)
 - Multi-module Optimization (two separate cases)

    
<details>
     <summary>  2-Input AND Gate</summary>
	
 #### Verilog Code:
The following Verilog module implements a 2-input AND gate. The output `y` is driven by the logical AND of inputs `a` and `b`, using a conditional assignment.

 ```verilog
 module opt_check(input a, input b, output y);
  assign y = a ? b : 0;
 endmodule
 ```

#### Steps for Synthesis:

   1. **Navigate to the Directory:**
         ```bash
         cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
         ```

   2. **Start the Yosys Tool:**
         ```bash
         yosys
         ```

   3. **Read the Library:**
         ```bash
         read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   4. **Read the Verilog File:**
         ```bash
         read_verilog opt_check.v
         ```

   5. **Synthesize the Design:**
         ```bash
         synth -top opt_check
![Screenshot from 2024-10-21 16-45-53](https://github.com/user-attachments/assets/6212c188-24be-46c3-874f-c8ded324022e)
         ```

   6. **Generate the Netlist:**
         ```bash
         abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   7. **Optimize the Design:**
         ```bash
         opt_clean -purge
         ```

   8. **Visualize the Schematic:**
         ```bash
         show
         ```
![Screenshot from 2024-10-21 16-46-04](https://github.com/user-attachments/assets/d05d692b-54ac-4f66-9492-c8e587b826d6)

</details>

<details>
      <summary> 2-Input OR Gate</summary>
<br>
	
#### Verilog Code:
The following Verilog code implements a 2-input OR gate. The output `y` is determined based on the logical OR of inputs `a` and `b`.

```verilog
module opt_check2(input a, input b, output y);
assign y = a ? 1 : b;
endmodule
```

#### Steps for Synthesis:

   1. **Navigate to the Directory:**
         ```bash
         cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
         ```

   2. **Start the Yosys Tool:**
         ```bash
         yosys
         ```

   3. **Read the Library:**
         ```bash
         read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   4. **Read the Verilog File:**
         ```bash
         read_verilog opt_check2.v
         ```

   5. **Synthesize the Design:**
         ```bash
         synth -top opt_check2
         ```
![Screenshot from 2024-10-21 16-47-38](https://github.com/user-attachments/assets/e836c1d2-a918-4b17-85b7-a724e5ce8b23)

   6. **Generate the Netlist:**
         ```bash
         abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   7. **Optimize the Design:**
         ```bash
         opt_clean -purge
         ```

   8. **Visualize the Schematic:**
         ```bash
         show
         ```
![Screenshot from 2024-10-21 16-47-59](https://github.com/user-attachments/assets/05df688c-090f-4f9c-96a4-5b5f64cad072)


</details>

<details>
      <summary> 3-Input AND Gate</summary>

   ### Verilog Code:
   This Verilog module describes a 3-input AND gate, where the output `y` is true if and only if all inputs (`a`, `b`, and `c`) are true.

```verilog
module opt_check3(input a, input b, input c, output y);
 assign y = a ? (b ? c : 0) : 0;
endmodule
```

 #### Steps for Synthesis:
   
   1. **Navigate to the Directory:**
         ```bash
         cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
         ```

   2. **Start the Yosys Tool:**
         ```bash
         yosys
         ```

   3. **Read the Library:**
         ```bash
         read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   4. **Read the Verilog File:**
         ```bash
         read_verilog opt_check3.v
         ```

   5. **Synthesize the Design:**
         ```bash
         synth -top opt_check3
         ```
![Screenshot from 2024-10-21 16-49-42](https://github.com/user-attachments/assets/6c8837e4-eea1-4f9e-b788-91fd270c3e51)

   6. **Generate the Netlist:**
         ```bash
         abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   7. **Optimize the Design:**
         ```bash
         opt_clean -purge
         ```

   8. **Visualize the Schematic:**
         ```bash
         show
         ```
![Screenshot from 2024-10-21 16-49-59](https://github.com/user-attachments/assets/389e71ba-5f25-448a-9524-d8ad8ff6ce3a)

</details>

<details>
      <summary> 2-Input XNOR Gate (3-Input Boolean Logic)</summary>

#### Verilog Code:
This Verilog module implements a 2-input XNOR gate using 3-input Boolean logic.

```verilog
module opt_check4(input a, input b, input c, output y);
assign y = a ? (b ? ~c : c) : ~c;
endmodule
```

#### Steps for Synthesis:
   
   1. **Navigate to the Directory:**
         ```bash
         cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
         ```

   2. **Start the Yosys Tool:**
         ```bash
         yosys
         ```

   3. **Read the Library:**
         ```bash
         read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   4. **Read the Verilog File:**
         ```bash
         read_verilog opt_check4.v
         ```

   5. **Synthesize the Design:**
         ```bash
         synth -top opt_check4
         ```
![Screenshot from 2024-10-21 16-51-07](https://github.com/user-attachments/assets/00e2e0d2-c945-4897-b99b-301e80a72dfc)

   6. **Generate the Netlist:**
         ```bash
         abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   7. **Optimize the Design:**
         ```bash
         opt_clean -purge
         ```

   8. **Visualize the Schematic:**
         ```bash
         show
         ```
![Screenshot from 2024-10-21 16-51-19](https://github.com/user-attachments/assets/34d45b61-46ee-4995-9c8f-7ebc89b48aa3)

</details>

<details>
      <summary> Multiple Module Optimization - 1</summary>

#### Verilog Code:
The following Verilog code describes a multi-module design using submodules for logic optimization.

```verilog
module sub_module1(input a, input b, output y);
assign y = a & b;
endmodule

module sub_module2(input a, input b, output y);
assign y = a ^ b;
endmodule

module multiple_module_opt(input a, input b, input c, input d, output y);
wire n1, n2, n3;

sub_module1 U1 (.a(a), .b(1'b1), .y(n1));
sub_module2 U2 (.a(n1), .b(1'b0), .y(n2));
sub_module2 U3 (.a(b), .b(d), .y(n3));

assign y = c | (b & n1);
endmodule
```

#### Steps for Synthesis:
   
   1. **Navigate to the Directory:**
         ```bash
         cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
         ```

   2. **Start the Yosys Tool:**
         ```bash
         yosys
         ```

   3. **Read the Library:**
         ```bash
         read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   4. **Read the Verilog File:**
         ```bash
         read_verilog multiple_module_opt.v
         ```

   5. **Synthesize the Design:**
         ```bash
         synth -top multiple_module_opt
         ```
![Screenshot from 2024-10-21 17-41-09](https://github.com/user-attachments/assets/4f85d082-3a88-4e47-a821-a52f4b8df05b)


   6. **Generate the Netlist:**
         ```bash
         abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   7. **Optimize the Design:**
         ```bash
         opt_clean -purge
         ```
   8. **Flattening merges hierarchies:**
         ```bash
         flatten
         ```
   9. **Visualize the Schematic:**
         ```bash
         show
         ```
![Screenshot from 2024-10-21 17-41-30](https://github.com/user-attachments/assets/2a67c8ef-d2e5-4c6e-bb62-37670544968d)


</details>

<details>
<summary> Multiple Module Optimization - 2</summary>

      
#### Verilog Code:

This is another example of multi-module optimization with a different configuration.

```verilog
module sub_module(input a, input b, output y);
assign y = a & b;
endmodule

module multiple_module_opt2(input a, input b, input c, input d, output y);
wire n1, n2, n3;
sub_module U1 (.a(a), .b(1'b0), .y(n1));
sub_module U2 (.a(b), .b(c), .y(n2));
sub_module U3 (.a(n2), .b(d), .y(n3));
sub_module U4 (.a(n3), .b(n1), .y(y));
endmodule
```

#### Steps for Synthesis:

   1. **Navigate to the Directory:**
         ```bash
         cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
         ```

   2. **Start the Yosys Tool:**
         ```bash
         yosys
         ```

   3. **Read the Library:**
         ```bash
         read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   4. **Read the Verilog File:**
         ```bash
         read_verilog multiple_module_opt2.v
         ```

   5. **Synthesize the Design:**
         ```bash
         synth -top multiple_module_opt2
         ```
![Screenshot from 2024-10-21 16-54-53](https://github.com/user-attachments/assets/68ff496b-eb26-4a84-8dae-2e427228f9ec)

   6. **Generate the Netlist:**
         ```bash
         abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
         ```

   7. **Optimize the Design:**
         ```bash
         opt_clean -purge
         ```
   8. **Flattening merges hierarchies:**
         ```bash
         flatten
         ```
   9. **Visualize the Schematic:**
         ```bash
         show
         ```
![Screenshot from 2024-10-21 17-38-41](https://github.com/user-attachments/assets/6c37234d-0a53-4245-95fd-aa75c31e8d23)



</details>

</details>
<details>
  <summary>Lab 2: Optimization of Various Sequential Designs</summary>
<br>
	
<details>
<summary>1. D-Flipflop Constant 1 with Asynchronous Reset (active low)</summary>
    
This section covers the implementation of a D Flip-Flop featuring an active low asynchronous reset. Below is the corresponding Verilog code:

   ```verilog
    module dff_const1(input clk, input reset, output reg q);
    always @(posedge clk or posedge reset) begin
        if (reset)
            q <= 1'b0;  // Output is set to 0 when reset is active
        else
            q <= 1'b1;  // Output is set to 1 on the rising edge of the clock
    end
    endmodule
    ```

The testbench designed to simulate the behavior of this D Flip-Flop is as follows:

   ```verilog
    module tb_dff_const1;
      reg clk, reset;
      wire q;

      dff_const1 uut (.clk(clk), .reset(reset), .q(q));

      initial begin
          $dumpfile("tb_dff_const1.vcd");
          $dumpvars(0, tb_dff_const1);
          // Initialize Inputs
          clk = 0;
          reset = 1;
          #3000 $finish; // End simulation after 3000 time units
      end

      always #10 clk = ~clk; // Generate clock signal with a period of 20 time units
      always #1547 reset = ~reset; // Toggle reset signal periodically
    endmodule
   ```

**Command Steps:**

To execute the design and observe the waveform, navigate to the required directory and execute the following commands:

   ```bash
    sudo -i
    cd ~
    cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

Use the following commands to compile and simulate the design:

   ```bash
    iverilog dff_const1.v tb_dff_const1.v
    ls
   ```

The `iverilog` command compiles the design and outputs an executable named `a.out`. To run this executable and observe the waveform, use:

   ```bash
    ./a.out
    gtkwave tb_dff_const1.vcd
   ```

![Screenshot from 2024-10-21 18-32-36](https://github.com/user-attachments/assets/b312c34a-16b5-44bc-b59f-5acd689b4226)

**Observation:** The waveform indicates that the output \( Q \) is high whenever the reset signal is low, showing that the reset operation is independent of the clock edge.

**Synthesis:**
    
To synthesize the design, navigate to the required directory again:

   ```bash
    sudo -i
    cd ~
    cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

Start Yosys and execute the following commands:

   ```bash
    yosys
    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    read_verilog dff_const1.v
    synth -top dff_const1
   ```

![Screenshot from 2024-10-21 18-40-35](https://github.com/user-attachments/assets/2b18eca5-8a14-4d8d-b6c4-d4caeb943fb1)

Generate the netlist with:

   ```bash
    dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

To create a graphical representation of the synthesized design, use:

   ```bash
    show
   ```

![Screenshot from 2024-10-21 18-40-59](https://github.com/user-attachments/assets/c4948e54-10e2-4f33-a810-bf24371414ef)

**Observation:** Since the reset condition does not rely on the clock edge, the D Flip-Flop remains unchanged in the synthesized output.

</details>

<details>
<summary>2. D-Flipflop Constant 2 with Asynchronous Reset (active high)</summary>
    
In this section, we explore a D Flip-Flop with an active high asynchronous reset. The Verilog implementation is as follows:

   ```verilog
    module dff_const2(input clk, input reset, output reg q);
    always @(posedge clk or posedge reset) begin
        if (reset)
            q <= 1'b1;  // Output is set to 1 when reset is active
        else
            q <= 1'b1;  // Output remains 1 on the rising edge of the clock
    end
    endmodule
   ```

The associated testbench code for this Flip-Flop is:

   ```verilog
    module tb_dff_const2;
      reg clk, reset;
      wire q;

      dff_const2 uut (.clk(clk), .reset(reset), .q(q));

      initial begin
          $dumpfile("tb_dff_const2.vcd");
          $dumpvars(0, tb_dff_const2);
          // Initialize Inputs
          clk = 0;
          reset = 1;
          #3000 $finish; // Terminate simulation after 3000 time units
      end

      always #10 clk = ~clk; // Generate clock signal
      always #1547 reset = ~reset; // Toggle reset signal
    endmodule
   ```

**Command Steps:**

To compile and simulate this design, navigate to the same directory:

   ```bash
    sudo -i
    cd ~
    cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

Execute the following commands:

   ```bash
    iverilog dff_const2.v tb_dff_const2.v
    ls
   ```

To run the simulation and view the waveform:

   ```bash
    ./a.out
    gtkwave tb_dff_const2.vcd
   ```

![Screenshot from 2024-10-21 18-37-16](https://github.com/user-attachments/assets/846315d9-6a7e-4c58-8aa8-8d3872619edb)

**Observation:** The waveform reveals that the output \( Q \) is consistently high, regardless of the reset signal.

**Synthesis:**

For synthesis, navigate to the directory again:

   ```bash
    sudo -i
    cd ~
    cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

Start Yosys and run these commands:

   ```bash
    yosys
    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    read_verilog dff_const2.v
    synth -top dff_const2
   ```

![Screenshot from 2024-10-21 18-43-10](https://github.com/user-attachments/assets/297a22b7-4465-44fc-934c-322afec48182)

Generate the netlist with:

   ```bash
    dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

To visualize the synthesized design, use:

   ```bash
    show
   ```


![Screenshot from 2024-10-21 18-43-43](https://github.com/user-attachments/assets/319b15e9-f087-4e95-8ae2-6f12968122d4)


**Observation:** The D Flip-Flop has been optimized away, as the output \( Q \) is always high and does not depend on the reset signal.

</details>

<details>
<summary>3. D-Flipflop Constant 3 with Synchronous Reset (active low)</summary>
    
Here, we examine a D Flip-Flop featuring a synchronous reset that is active low. The Verilog code for this configuration is as follows:

   ```verilog
    module dff_const3(input clk, input reset, output reg q);
    reg q1;

    always @(posedge clk or posedge reset) begin
        if (reset) begin
            q <= 1'b1;  // Output set to 1 when reset is active
            q1 <= 1'b0; // Intermediate register q1 set to 0
        end else begin	
            q1 <= 1'b1; // Intermediate register q1 set to 1
            q <= q1;    // Output q updates to q1's value
        end
    end
    endmodule
   ```

The corresponding testbench code is provided below:

   ```verilog
    module tb_dff_const3;
      reg clk, reset;
      wire q;

      dff_const3 uut (.clk(clk), .reset(reset), .q(q));

      initial begin
          $dumpfile("tb_dff_const3.vcd");
          $dumpvars(0, tb_dff_const3);
          // Initialize Inputs
          clk = 0;
          reset = 1;
          #3000 $finish; // End simulation after 3000 time units
      end

      always #10 clk = ~clk; // Generate clock signal
      always #1547 reset = ~reset; // Toggle reset signal
    endmodule
   ```

**Synthesis:**

Again, navigate to the required directory:

   ```bash
    sudo -i
    cd ~
    cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

Start Yosys and execute the following commands:

   ```bash
    yosys
    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    read_verilog dff_const3.v
    synth -top dff_const3
   ```

![Screenshot from 2024-10-21 18-46-57](https://github.com/user-attachments/assets/cf20c804-ed6b-46e5-a3fa-bfb0e7364642)

Generate the netlist:

   ```bash
    dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

To create a graphical representation of the synthesized design:

   ```bash
    show
   ```

![Screenshot from 2024-10-21 18-47-11](https://github.com/user-attachments/assets/28817899-84d5-4044-b649-62c9186f1191)


**Observation:** This module illustrates that on reset, \( Q \) is set to 1 while \( q1 \) is reset to 0. On each clock cycle, \( q1 \) is updated to 1, and \( Q \) reflects the value of \( q1 \).

</details>

<details>
<summary>4. D-Flipflop Constant 4 with Synchronous Reset (active high)</summary>
    
In this section, we explore a D Flip-Flop with a synchronous reset that is active high. The Verilog code implementation is as follows:

   ```verilog
    module dff_const4(input clk, input reset, output reg q);
    reg q1;

    always @(posedge clk or posedge reset) begin
        if (reset) begin
            q <= 1'b1;  // Output set to 1 when reset is active
            q1 <= 1'b1; // Intermediate register q1 also set to 1
        end else begin	
            q1 <= 1'b1; // Intermediate register q1 set to 1
            q <= q1;    // Output q updates to the value of q1
        end
    end
    endmodule
   ```

**Synthesis:**

To synthesize this design, navigate to the required directory:

   ```bash
    sudo -i
    cd ~
    cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

Launch Yosys and run the following commands:

   ```bash
    yosys
    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    read_verilog dff_const4.v
    synth -top dff_const4
   ```
![Screenshot from 2024-10-21 18-48-44](https://github.com/user-attachments/assets/d954d657-b695-4473-a554-50848c7b0696)

Generate the netlist:

   ```bash
    dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

Finally, create a graphical representation:

   ```bash
    show
   ```
![Screenshot from 2024-10-21 18-48-57](https://github.com/user-attachments/assets/d1ed60d4-80dd-4033-8b1c-b08453f14333)

**Observation:** This module specifies that both \( q \) and \( q1 \) are set to 1 upon a positive edge of reset. Consequently, \( Q \) maintains a value of 1, regardless of clock or reset states.

</details>

<details>
<summary>5. D-Flipflop Constant 5 with Synchronous Reset</summary>
    
This section presents a D Flip-Flop with a synchronous reset. The Verilog code is as follows:

   ```verilog
    module dff_const5(input clk, input reset, output reg q);
    reg q1;

    always @(posedge clk or posedge reset) begin
        if (reset) begin
            q <= 1'b0;  // Output is set to 0 when reset is active
            q1 <= 1'b0; // Intermediate register q1 also reset to 0
        end else begin	
            q1 <= 1'b1; // Intermediate register q1 set to 1
            q <= q1;    // Output q is updated to q1's value
        end
    end
    endmodule
   ```

**Synthesis:**

To synthesize this design, navigate to the required directory:

   ```bash
    sudo -i
    cd ~
    cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

Launch Yosys and execute:

   ```bash
    yosys
    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    read_verilog dff_const5.v
    synth -top dff_const5
   ```
![Screenshot from 2024-10-21 18-51-09](https://github.com/user-attachments/assets/53e4d944-1908-46a5-9dcf-5410acddd590)

Generate the netlist with:

   ```bash
    dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

Create a graphical representation:

   ```bash
    show
   ```
![Screenshot from 2024-10-21 18-51-26](https://github.com/user-attachments/assets/6c607f85-0ea5-4c8f-8ed9-b8d19d426b8e)

**Observation:** This module defines a D Flip-Flop that resets both \( q \) and \( q1 \) to 0 on a positive edge of reset. On each clock cycle, \( q1 \) is set to 1, and \( q \) is updated accordingly. Therefore, after the first clock cycle following reset, \( Q \) remains 1.

</details>

<details>
<summary>6. Counter Optimization 1</summary>
    
This section covers the implementation of a simple counter optimized for operation. The Verilog code is:

   ```verilog
    module counter_opt(input clk, input reset, output q);
    reg [2:0] count; // 3-bit counter
    assign q = count[0]; // Output assigned to the least significant bit of count
    
    always @(posedge clk or posedge reset) begin
        if (reset)
            count <= 3'b000; // Reset counter to 0
        else
            count <= count + 1; // Increment counter on clock edge
    end
    endmodule
   ```

**Synthesis:**

For synthesis, navigate to the required directory:

   ```bash
    sudo -i
    cd ~
    cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

Launch Yosys and run:

   ```bash
    yosys
    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    read_verilog counter_opt.v
    synth -top counter_opt
   ```
![Screenshot from 2024-10-21 18-55-35](https://github.com/user-attachments/assets/d709f510-3580-471e-b559-e3e5e1b87752)

Generate the netlist with:

   ```bash
    dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

Create a graphical representation:

   ```bash
    show
   ```
![Screenshot from 2024-10-21 18-55-59](https://github.com/user-attachments/assets/deb39cb1-4a1b-4c94-9902-2eaa714e2c44)

</details>

<details>
<summary>7. Counter Optimization 2</summary>
    
This section presents an optimized counter design. The Verilog code is as follows:

   ```verilog
    module counter_opt2(input clk, input reset, output q);
    reg [2:0] count; // 3-bit counter
    assign q = (count[2:0] == 3'b100); // Output set high when count reaches 4
    
    always @(posedge clk or posedge reset) begin
        if (reset)
            count <= 3'b000; // Reset counter to 0
        else
            count <= count + 1; // Increment counter on clock edge
    end
    endmodule
   ```

**Synthesis:**

To synthesize this design, navigate to the required directory:

   ```bash
    sudo -i
    cd ~
    cd /home/yerasi-manoj-reddy/VLSI/sky130RTLDesignAndSynthesisWorkshop/verilog_files
   ```

Launch Yosys and execute:

   ```bash
    yosys
    read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
    read_verilog counter_opt2.v
    synth -top counter_opt
   ```
![Screenshot from 2024-10-21 19-02-02](https://github.com/user-attachments/assets/4ae990c4-d14b-4603-adc8-b46c53ea19d6)

Generate the netlist with:

   ```bash
    dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   ```

Finally, create a graphical representation:

   ```bash
    show
   ```
![Screenshot from 2024-10-21 19-02-28](https://github.com/user-attachments/assets/a46ad1d8-3f47-4a04-a248-de952a7997f9)

  </details>

</details>

</details>
<details>
<summary> Day-4</summary>
	<br>

## AIM: Gate Level Simulation (GLS), Synthesis-Simulation Mismatch, Non-blocking and Blocking Statements

Gate Level Simulation (GLS) is an essential component of the digital design verification process. It serves as a critical checkpoint where designers can verify the accuracy and functionality of the synthesized netlist, which represents a more refined and lower-level view of the design than the original high-level abstraction. The GLS process involves running simulations using a testbench to assess both the logical correctness and the timing performance of the circuit. By examining the output waveforms and comparing them with expected results, designers can ensure that the synthesis process has not inadvertently introduced errors that could affect the overall functionality of the design. This stage is particularly vital as it provides insights into how well the design meets the required specifications and performance criteria before moving on to the physical implementation.

One of the key aspects of GLS is the consideration of sensitivity lists in the design. These lists are crucial for ensuring that the circuit behaves correctly under all conditions. An incomplete sensitivity list can lead to unintended latches in the design, which may result in synthesis and simulation mismatches. Furthermore, the distinction between blocking and non-blocking assignments is significant in this context. Blocking assignments, which execute sequentially, can create scenarios where the output does not respond to changes in input as expected, leading to potential errors in the simulated behavior. Non-blocking assignments, on the other hand, allow for concurrent execution and can help prevent such issues. Thus, careful analysis of the circuit's behavior, combined with a thorough understanding of sensitivity lists and assignment types, is necessary to achieve accurate results in GLS.

### GLS Simulation

### Example 1: 2 x 1 Multiplexer Using Ternary Operator

**Verilog Code:**
```verilog
module ternary_operator_mux (input i0, input i1, input sel, output y);
    assign y = sel ? i1 : i0;
endmodule
```

### Command Steps for Simulation:
```bash
iverilog ternary_operator_mux.v tb_ternary_operator_mux.v
./a.out
gtkwave tb_ternary_operator_mux.vcd
```
![Screenshot from 2024-10-21 20-19-43](https://github.com/user-attachments/assets/74904c0f-cf5a-4f60-9c49-b1ce05975a51)

### Synthesis:
This will invoke/start Yosys.
```bash
yosys
```

**Read the Library:**
```bash
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
**Read the Design Verilog Files:**
```bash
read_verilog ternary_operator_mux.v
```
**Synthesize the Design:**
```bash
synth -top ternary_operator_mux
```
**Generate the Netlist:**
```bash
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
**Create a Graphical Representation:**
```bash
show
```
![Screenshot from 2024-10-21 20-23-09](https://github.com/user-attachments/assets/711af227-7e78-4366-9a99-eacc83dec86d)

### To See the Netlist:
```bash
write_verilog -noattr ternary_operator_mux_net.v
!gvim ternary_operator_mux_net.v
```
![Screenshot from 2024-10-21 20-25-08](https://github.com/user-attachments/assets/8624c46a-e43b-4951-b9c3-75549cbee1e2)

### Gate Level Synthesis (GLS)

### Command Steps:
Go to the required directory:
```bash
sudo -i
cd ~
cd /home/yerasi-manoj-reddy/vlsi/sky130RTLDesignAndSynthesisWorkshop/verilog_files
```

We just need to put a few commands as stated below in order to see the waveforms.
```bash
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v ternary_operator_mux_net.v tb_ternary_operator_mux.v
ls
```

After giving the above command the IVerilog stores the output as ' a.out '

Now let's execute the ' a.out ' file and observe the waveforms.
```bash
./a.out
gtkwave tb_ternary_operator_mux.vcd
```

Below is the Snapshot of the above commands and the resultant Waveforms:
![Screenshot from 2024-10-21 20-31-18](https://github.com/user-attachments/assets/d27d6e78-b964-4def-ae88-ab5a67c28607)

These waveforms correspond to the GATE LEVEL SYNTHESIS for the Ternary Operator MUX.

### Example 2: Design of a 2:1 Bad MUX

**Verilog Code:**
```verilog
module bad_mux(input i0, input i1, input sel, output reg y);
	always@(sel)
	begin
		if(sel)
			y <= i1;
		else
			y <= i0;
	end
endmodule
```
### Command Steps for Simulation:
```bash
iverilog bad_mux.v tb_bad_mux.v
./a.out
gtkwave tb_bad_mux.vcd
```
![Screenshot from 2024-10-21 20-36-54](https://github.com/user-attachments/assets/c9cfa574-c89b-4312-9aa6-0e47e03690a7)

From the waveform, it can be observed that the output y changes only when there is a change in the select line, completely ignoring the change in i0 and i1, which should also change the output y. Thus, this design is that of a bad MUX.

### Synthesis:
This will invoke/start Yosys.
```bash
yosys
```
**Read the Library:**
```bash
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
**Read the Design Verilog Files:**
```bash
read_verilog bad_mux.v
```
**Synthesize the Design:**
```bash
synth -top bad_mux
```
**Generate the Netlist:**
```bash
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
**Create a Graphical Representation:**
```bash
show
```
![Screenshot from 2024-10-21 20-38-02](https://github.com/user-attachments/assets/c5019258-51e7-4858-83df-3d1092ebd76e)

### To See the Netlist:
```bash
write_verilog -noattr bad_mux_net.v
!gvim bad_mux_net.v
```
![Screenshot from 2024-10-21 20-39-23](https://github.com/user-attachments/assets/bf8ad5a8-d84c-4d32-97be-334df23669ca)

From the waveform, it can be observed that the output y changes only when there is a change in the select line, completely ignoring the change in i0 and i1, which should also change the output y. Thus, this design is that of a bad MUX.

### Gate Level Synthesis (GLS)

### Command Steps:
Go to the required directory:
```bash
sudo -i
cd ~
cd /home/yerasi-manoj-reddy/vlsi/sky130RTLDesignAndSynthesisWorkshop/verilog_files
```

We just need to put a few commands as stated below in order to see the waveforms.
```bash
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v bad_mux.v tb_bad_mux.v
ls
```

After giving the above command, the IVerilog stores the output as ' a.out '

Now let's execute the ' a.out ' file and observe the waveforms.
```bash
./a.out
gtkwave tb_bad_mux.vcd
```
Below is the Snapshot of the above commands and the resultant Waveforms:
![Screenshot from 2024-10-21 20-44-34](https://github.com/user-attachments/assets/d431486b-8e76-4361-9363-07029250affe)

These waveforms correspond to the GATE LEVEL SYNTHESIS for the Bad MUX.

### Example 3: Blocking Caveat

**Verilog Code:**
```verilog
module blocking_caveat(input a, input b, input c, output reg d);
	reg x;

	always@(*)
	begin
		d = x & c;
		x = a | b;
	end
endmodule
```

### Command Steps for Simulation:
```bash
iverilog blocking_caveat.v tb_blocking_caveat.v
./a.out
gtkwave tb_blocking_caveat.vcd
```
![Screenshot from 2024-10-21 20-46-26](https://github.com/user-attachments/assets/4d6dd6b5-6aaf-4ac5-b4bc-a02ec86c319e)

As depicted, when A and B go zero, the OR gate output should be zero (X equal to zero), and the AND gate output should also be zero (same as D output). But, the AND gate input of X takes the previous value of A|B equal to one, based on the design created by the blocking statement, hence the discrepancy in the output.

### Synthesis:
This will invoke/start Yosys.
```bash
yosys
```

**Read the Library:**
```bash
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

**Read the Design Verilog Files:**
```bash
read_verilog blocking_caveat.v
```

**Synthesize the Design:**
```bash
synth -top blocking_caveat
```

**Generate the Netlist:**
```bash
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```

**Create a Graphical Representation:**
```bash
show
```
![Screenshot from 2024-10-21 20-48-05](https://github.com/user-attachments/assets/ba5d0b43-8c89-4e18-8a97-0be6eac6e69e)

### To See the Netlist:
```bash
write_verilog -noattr blocking_caveat_net.v
!gvim blocking_caveat_net.v
```
![Screenshot from 2024-10-21 20-48-44](https://github.com/user-attachments/assets/5b130e9f-5799-4935-a456-19888f1ea0ab)

### Gate Level Synthesis (GLS)

### Command Steps:
Go to the required directory:
```bash
sudo -i
cd ~
cd /home/yerasi-manoj-reddy/vlsi/sky130RTLDesignAndSynthesisWorkshop/verilog_files
```

We just need to put a few commands as stated below in order to see the waveforms.
```bash
iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v blocking_caveat_net.v tb_blocking_caveat.v
ls
```

After giving the above command, the IVerilog stores the output as ' a.out '

Now let's execute the ' a.out ' file and observe the waveforms.
```bash
./a.out
gtkwave tb_blocking_caveat.vcd
```

Below is the Snapshot of the above commands and the resultant Waveforms:
![Screenshot from 2024-10-21 20-49-58](https://github.com/user-attachments/assets/542d7087-78d3-41e5-b36d-f7868ed710df)

These waveforms correspond to the GATE LEVEL SYNTHESIS for the Blocking Caveat.

</details>
</details>
<details> 
	<summary>ASIC Lab 9</summary>
	<br>

# TASK 11: Synthesize RISC-V and Compare Output with Functional Simulations
 
**Objective:**  
The goal of this task is to synthesize the RISC-V design and compare its output with functional simulations.

---

### Steps:

1. **Copy the source folder:**  
   Begin by copying the `src` folder from the VSDBabySoC directory into the `vlsi` folder. Then, copy it into the `sky130RTLDesignAndSynthesisWorkshop` directory using the following commands:
```
   sudo -i  
   cd /home/yerasi-manoj-reddy/vlsi/  
   cp -r src sky130RTLDesignAndSynthesisWorkshop/
```
2. **Navigate to the required directory:**  
   Move to the target directory where synthesis will take place:
```
   cd ~  
   cd /home/yerasi-manoj-reddy/vlsi/sky130RTLDesignAndSynthesisWorkshop/src/module
```

### Synthesis:

3. **Start Yosys for synthesis:**  
   Invoke Yosys by entering the following command:
 ```
   yosys
```
4. **Read the library:**  
   Load the standard cell library required for synthesis:
```
   read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
5. **Read the Verilog design files:**  
   Import the required Verilog files for clock gating and RISC-V designs:
```
   read_verilog clk_gate.v  
   read_verilog rvmyth.v
```
6. **Synthesize the design:**  
   Synthesize the top-level module `rvmyth`:
```bash
   synth -top rvmyth
   abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
   show
```
![Screenshot from 2024-10-23 21-49-59](https://github.com/user-attachments/assets/60799757-1a12-4cab-9b3d-817aaeaad03c)
![Screenshot from 2024-10-23 21-50-11](https://github.com/user-attachments/assets/ba6fa5a1-965c-412a-8ae2-bf28bb7e048a)
![Screenshot 2024-10-23 213342](https://github.com/user-attachments/assets/ee01fdcf-c276-4964-afe6-5b5bbfb08bfe)

7. **Generate the netlist:**  
   After synthesis, generate the netlist and inspect it:
```  
   write_verilog -noattr rvmyth.v  
   !gvim rvmyth.v  
   exit
```
![Screenshot from 2024-10-24 01-06-32](https://github.com/user-attachments/assets/20a8c0e4-1b0a-4c7a-9f9b-8f0618fb6936)

### Simulate the Synthesized Design:

8. **Observe the synthesized RISC-V output waveform:**  
   Use the following commands to run the simulation and view the waveforms:
```
   iverilog ../../my_lib/verilog_model/primitives.v ../../my_lib/verilog_model/sky130_fd_sc_hd.v rvmyth.v testbench.v vsdbabysoc.v avsddac.v avsdpll.v clk_gate.v  
   ls  
   ./a.out  
   gtkwave dump.vcd
```

### Functional Simulations:

9. **Simulate functional design:**  
   Navigate to the VSDBabySoC directory and simulate the pre-synthesized version of the design:
```
   cd ~  
   cd VSDBabySoC  
   iverilog -o ./pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module/  
   ./pre_synth_sim.out  
   gtkwave pre_synth_sim.vcd
```

### Comparison:

10. **Comparison of Functionality vs Synthesized Output:**  
    Finally, compare the waveforms of the functional and synthesized simulations to verify correctness.
## O1
![Screenshot from 2024-10-24 00-28-27](https://github.com/user-attachments/assets/fcc2b8c7-4b28-4f29-b19f-727f3a5a2383)
## O2
![Screenshot from 2024-10-24 01-45-42](https://github.com/user-attachments/assets/21019be8-0029-4536-92e8-2164504b7985)

## Observation:
we can see that O1 = O2 so functionality is equal to synthesized Output.
</details>
<details>
	<summary> ASIC Lab 10</summary>
	<br>

# Static Timing Analysis for a Synthesized RISC-V Core with OpenSTA 
## Installation of Tools

### CUDD
Begin by downloading CUDD from this **[source](https://github.com/davidkebo/cudd/blob/main/cudd_versions/cudd-3.0.0.tar.gz)**. Once downloaded, move the file to your home directory for easy access.

```bash
cd
tar xvfz cudd-3.0.0.tar.gz
cd cudd-3.0.0
./configure
make
```
![Screenshot from 2024-10-28 21-39-38](https://github.com/user-attachments/assets/80f297e2-dd87-4e3b-9237-2cd53cbbe8ae)

### openSTA Setup

Next, install openSTA. Start by updating your system and ensuring you have the necessary packages.

```bash
cd
sudo apt-get install cmake clang gcc tcl swig bison flex

git clone https://github.com/parallaxsw/OpenSTA.git
cd OpenSTA
cmake -DCUDD_DIR=/home/yerasi-manoj-reddy/cudd-3.0.0
make
app/sta
```

```bash
cd /home/yerasi-manoj-reddy/OpenSTA
mkdir lab10
```

Ensure you move all the necessary files into the newly created directory named `lab10`.

## Timing Analysis Procedure

When conducting timing analysis, adhere to the following parameters:

- The specified clock period is 9.8 nanoseconds.
- The setup uncertainty and clock transition should be 5% of the clock period.
- The hold uncertainty and data transition should account for 8% of the clock period.

Execute the following commands to perform the analysis:

```bash
cd /home/yerasi-manoj-reddy/OpenSTA/app
./sta

read_liberty /home/yerasi-manoj-reddy/OpenSTA/lab10/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog /home/yerasi-manoj-reddy/OpenSTA/lab10/manoj_riscv_netlist.v
link_design rvmyth

create_clock -name clk -period 9.8 [get_ports clk]
set_clock_uncertainty [expr 0.05 * 9.8] -setup [get_clocks clk]
set_clock_uncertainty [expr 0.08 * 9.8] -hold [get_clocks clk]
set_clock_transition [expr 0.05 * 9.8] [get_clocks clk]
set_input_transition [expr 0.08 * 9.8] [all_inputs]


```
To execute the OpenSTA and obtain the timing reports, run the below command,
```
sta scripts/sta.conf
```
Following are contents of the sta.conf file,
```
read_liberty -min ./lib/sta/sky130_fd_sc_hd__tt_025C_1v80.lib
read_liberty -max ./lib/sta/sky130_fd_sc_hd__tt_025C_1v80.lib
read_liberty -min ./lib/avsdpll.lib
read_liberty -max ./lib/avsdpll.lib
read_liberty -min ./lib/avsddac.lib
read_liberty -max ./lib/avsddac.lib
read_verilog ./src/module/vsdbabysoc_synth.v
link_design vsdbabysoc
read_sdc ./src/sdc/sta_post_synth.sdc
```
![Screenshot from 2024-10-28 21-41-13](https://github.com/user-attachments/assets/45c4dc83-6861-4a7b-a1d4-c4191a7a9743)
```
report_checks -path_delay max
```
![Screenshot from 2024-10-28 20-38-02](https://github.com/user-attachments/assets/070794d1-5836-4dbd-a31b-3e98753eedb5)
```
report_checks -path_delay min
```
![Screenshot from 2024-10-28 20-38-09](https://github.com/user-attachments/assets/789a3cd2-c367-41cc-83b2-92e77b703bcc)

</details>
<details>
	<summary> ASIC Lab 11</summary>

 <br>

 # Lab11: PVT Corner Analysis for Synthesized VSDBabySoC using OpenSTA

The PVT corner refers to the combination of Process, Voltage, and Temperature variations that a semiconductor chip might encounter during its operation. These variations can affect the performance, power consumption, and reliability of the chip, so they are simulated to ensure the chip functions correctly under different conditions. The below tcl script `sta_pvt.tcl` can be run to perform the STA across the PVT corners for which the sky130 lib files are available:

# List of library files for PVT corners
```
set list_of_lib_files(1) "sky130_fd_sc_hd__ff_100C_1v65.lib"
set list_of_lib_files(2) "sky130_fd_sc_hd__ff_100C_1v95.lib"
set list_of_lib_files(3) "sky130_fd_sc_hd__ff_n40C_1v56.lib"
set list_of_lib_files(4) "sky130_fd_sc_hd__ff_n40C_1v65.lib"
set list_of_lib_files(5) "sky130_fd_sc_hd__ff_n40C_1v76.lib"
set list_of_lib_files(6) "sky130_fd_sc_hd__ff_n40C_1v95.lib"
set list_of_lib_files(7) "sky130_fd_sc_hd__ss_100C_1v40.lib"
set list_of_lib_files(8) "sky130_fd_sc_hd__ss_100C_1v60.lib"
set list_of_lib_files(9) "sky130_fd_sc_hd__ss_n40C_1v28.lib"
set list_of_lib_files(10) "sky130_fd_sc_hd__ss_n40C_1v35.lib"
set list_of_lib_files(11) "sky130_fd_sc_hd__ss_n40C_1v40.lib"
set list_of_lib_files(12) "sky130_fd_sc_hd__ss_n40C_1v44.lib"
set list_of_lib_files(13) "sky130_fd_sc_hd__ss_n40C_1v60.lib"
set list_of_lib_files(14) "sky130_fd_sc_hd__ss_n40C_1v76.lib"
set list_of_lib_files(15) "sky130_fd_sc_hd__tt_025C_1v80.lib"
set list_of_lib_files(16) "sky130_fd_sc_hd__tt_100C_1v80.lib"
for {set i 1} {$i <= [array size list_of_lib_files]} {incr i} {
    read_liberty /home/yerasi-manoj-reddy/VSDBabySoC/src/timing_libs/$list_of_lib_files($i)
    read_verilog /home/yerasi-manoj-reddy/VSDBabySoC/src/module/vsdbabysoc.synth.v
    link_design rvmyth
    read_sdc /home/yerasi-manoj-reddy/VSDBabySoC/src/sdc/vsdbabysoc_synthesis.sdc
    check_setup -verbose
    report_checks -path_delay min_max -fields {nets cap slew input_pins fanout} -digits {4} > /home/yerasi-manoj-reddy/VSDBabySoC/src/sta_output/min_max_$list_of_lib_files($i).txt

    exec echo "$list_of_lib_files($i)" >> /home/yerasi-manoj-reddy/VSDBabySoC/src/sta_output/sta_worst_max_slack.txt
    report_worst_slack -max -digits {4} >> /home/yerasi-manoj-reddy/VSDBabySoC/src/sta_output/sta_worst_max_slack.txt

    exec echo "$list_of_lib_files($i)" >> /home/yerasi-manoj-reddy/VSDBabySoC/src/sta_output/sta_worst_min_slack.txt
    report_worst_slack -min -digits {4} >> /home/yerasi-manoj-reddy/VSDBabySoC/src/sta_output/sta_worst_min_slack.txt

    exec echo "$list_of_lib_files($i)" >> /home/yerasi-manoj-reddy/VSDBabySoC/src/sta_output/sta_tns.txt
    report_tns -digits {4} >> /home/yerasi-manoj-reddy/VSDBabySoC/src/sta_output/sta_tns.txt

    exec echo "$list_of_lib_files($i)" >> /home/yerasi-manoj-reddy/VSDBabySoC/src/sta_output/sta_wns.txt
    report_wns -digits {4} >> /home/yerasi-manoj-reddy/VSDBabySoC/src/sta_output/sta_wns.txt
}
```
![Screenshot from 2024-11-05 01-50-34](https://github.com/user-attachments/assets/cba1609d-190d-458c-99f6-4d854145d360)

![Screenshot from 2024-11-05 01-30-21](https://github.com/user-attachments/assets/aa03fe73-3588-44cb-91a9-2dd4a91f8e63)


The SDC file used for generating clock and data constraints is given below:

# SDC constraints for VSDBabySoC
```
set PERIOD 9.80
set_units -time ns
create_clock [get_ports {clk}] -name clk -period $PERIOD
set_clock_uncertainty -setup  [expr $PERIOD * 0.05] [get_clocks clk]
set_clock_transition [expr $PERIOD * 0.05] [get_clocks clk]
set_clock_uncertainty -hold [expr $PERIOD * 0.08] [get_clocks clk]
set_input_transition [expr $PERIOD * 0.08] [get_ports ENb_CP]
set_input_transition [expr $PERIOD * 0.08] [get_ports ENb_VCO]
set_input_transition [expr $PERIOD * 0.08] [get_ports REF]
set_input_transition [expr $PERIOD * 0.08] [get_ports VCO_IN]
set_input_transition [expr $PERIOD * 0.08] [get_ports VREFH]
```
![Screenshot from 2024-11-08 13-00-18](https://github.com/user-attachments/assets/6599984d-2491-472f-ae8a-578cf625278d)


Run below commands on terminal to source the `sta_pvt.tcl` file:
```
source /home/yerasi-manoj-reddy/VSDBabySoC/src/tcl/sta_pvt.tcl
```
## Analysis Report
### table of slack report:
![Screenshot from 2024-11-05 00-26-32](https://github.com/user-attachments/assets/34c35f5f-1bd9-432c-8b00-693e072b6e95)
### Total Negative Slack:
![Screenshot from 2024-11-05 00-00-42](https://github.com/user-attachments/assets/0d53f59c-04be-40a4-ba76-44b7de647f76)
### Worst (Negative slack)Setup Slack:
![Screenshot from 2024-11-04 23-52-28](https://github.com/user-attachments/assets/0dd7b615-1bfe-4b3a-b160-cad08b91095a)
### Worst Setup Slack:
![Screenshot from 2024-11-05 00-22-54](https://github.com/user-attachments/assets/3529f44b-b6c9-413c-918c-c13c92a384ba)
### Worst Hold Slack:
![Screenshot from 2024-11-05 00-20-44](https://github.com/user-attachments/assets/a180b970-e71e-4859-9d51-b2763a2a6b49)

The analysis report shows the following key points:

1. **Worst Setup Slack**: `sky130_fd_sc_hd__ss_n40C_1v28.lib` library file has the worst setup slack.
2. **Worst Hold Slack**: `sky130_fd_sc_hd__ff_100C_1v95.lib` library file has the worst hold slack.

The total negative slack and worst negative slacks are provided in the detailed slacks report screenshots.

</details>
<details>
	<summary>ASIC Lab 12</summary>
	<br>

 # Digital VLSI SoC Design and Planning

 <details>
<summary>Day 1</summary>
	 <br>
	 
### Section 1: Introduction to Open-Source EDA, OpenLANE, and Sky130 PDK  

**Theory**:  
This section focuses on the fundamentals of open-source EDA tools, specifically using OpenLANE and the Sky130 PDK.

**Implementation**  
**Tasks**:
1. Run the `picorv32a` design synthesis using the OpenLANE flow and generate relevant outputs.

#### OpenLANE Flow - Synthesis Commands
```
# Navigate to the OpenLANE working directory
cd Desktop/work/tools/openlane_working_dir/openlane

# Start Docker container
docker

# Launch OpenLANE in interactive mode
./flow.tcl -interactive

# Load OpenLANE package
package require openlane 0.9

# Prepare design for 'picorv32a'
prep -design picorv32a

# Run synthesis
run_synthesis

# Exit OpenLANE
exit

# Exit Docker
exit
```
**Screenshots**:  
![1](https://github.com/user-attachments/assets/10bf6d0f-df1f-4509-b9df-7a63a15264c2)
![2](https://github.com/user-attachments/assets/f4f64fda-a093-41f3-bb84-b927227198aa)

2. Calculate the **flop ratio**:
![3](https://github.com/user-attachments/assets/7d1b5a26-aecf-4680-8849-e6b77ebe2f72)
   **Formula**:  
   ```
   Flop Ratio = (Number of D Flip-Flops) / (Total Number of Cells)  
   DFF Percentage = Flop Ratio * 100
   ```

   **Results**:
   ```
   Flop Ratio = 1613 / 14876 = 0.1084  
   DFF Percentage = 0.1084 * 100 = 10.84%
   ```
---

</details>
<details>
	<summary>Day 2</summary>
	<br>
	
### Section 2: Floorplanning and Library Cell Introduction  

**Theory**:  
This section covers the differences between good and bad floorplanning and introduces library cells.

**Implementation**  
**Tasks**:
1. Run the `picorv32a` floorplan using the OpenLANE flow.
2. Calculate the die area in microns based on the floorplan `.def` file.
3. Load the floorplan `.def` file in Magic tool to analyze it.
4. Perform congestion-aware placement and explore the results in Magic.

   **Die Area Calculation**:
   ```
   Area of Die = Die Width (in microns) × Die Height (in microns)
   ```

#### OpenLANE Flow - Floorplan Commands
```
# Navigate to the OpenLANE working directory
cd Desktop/work/tools/openlane_working_dir/openlane

# Start Docker container
docker

# Launch OpenLANE in interactive mode
./flow.tcl -interactive

# Load OpenLANE package
package require openlane 0.9

# Prepare design for 'picorv32a'
prep -design picorv32a

# Run synthesis
run_synthesis

# Run floorplan
run_floorplan
```
**Screenshots**:  
![4](https://github.com/user-attachments/assets/06dccc75-6396-4596-83bd-29917bfea24b)
![5](https://github.com/user-attachments/assets/8c54066d-1336-4ac7-9206-6f7e1af672dd)

## 2. Die Area Calculation from `.def` file:
![6](https://github.com/user-attachments/assets/239301cb-3569-42a8-a494-09b84d742f22)

```
Unit Distance = 1 Micron  
Die Width (units) = 660685  
Die Height (units) = 671405  

Die Width (microns) = 660685 / 1000 = 660.685  
Die Height (microns) = 671405 / 1000 = 671.405  

Area of Die (square microns) = 660.685 × 671.405 = 443587.21 µm²
```
### 3. Load generated floorplan `.def` in Magic tool and explore the floorplan.

#### Commands to Load Floorplan `.def` in Magic (in another terminal)
```
# Change directory to path containing generated floorplan .def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/17-03_12-06/results/floorplan/

# Command to load the floorplan .def in Magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```

**Screenshots of Floorplan in Magic**:
- **Generated Floorplan Loaded in Magic**  
![7](https://github.com/user-attachments/assets/7fb737f4-7e87-4090-9a34-27478ff1254b)

- **Equidistant Placement of Ports**  
![8](https://github.com/user-attachments/assets/d74af718-122a-4ab9-bc86-a429d9b8ca83)

- **Port Layer Configuration as set through `config.tcl`**  
![9](https://github.com/user-attachments/assets/2efeaaf7-7831-44ea-9f86-d43e6b3c70e1)

- **Decap Cells and Tap Cells**  
![10](https://github.com/user-attachments/assets/ee95acaa-690b-4380-9067-e3630cf8b4cd)

- **Diagonally Equidistant Tap Cells**  
![11](https://github.com/user-attachments/assets/502b7c91-aa4a-41f4-83a0-ac08fb4275a1)

- **Unplaced Standard Cells at the Origin**  
![12](https://github.com/user-attachments/assets/66002698-95d0-44c4-8396-a4df8a6da452)
4. Run 'picorv32a' Design Congestion Aware Placement using OpenLANE Flow

#### Command to Run Placement
```
# Congestion aware placement by default
run_placement
```

**Screenshots of Placement Run**:
- Screenshot from 2024-03-17 22-44-17  
![13](https://github.com/user-attachments/assets/922d4e76-30ee-4b49-934f-336adf8f6378)


---

### 5. Load Generated Placement `.def` in Magic Tool and Explore the Placement

#### Commands to Load Placement `.def` in Magic (in another terminal)
```
# Change directory to path containing generated placement .def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/17-03_12-06/results/placement/

# Command to load the placement .def in Magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```

**Screenshots of Placement in Magic**:
- **Generated Placement Loaded in Magic**  
![14](https://github.com/user-attachments/assets/89ee243c-39dc-472d-8585-2b7d31f099ca)

- **Standard Cells Legally Placed**  
![15](https://github.com/user-attachments/assets/4b2e07b2-712d-4294-ac73-e55b82daab9d)


---

#### Commands to Exit from Current Run
```
# Exit from OpenLANE flow
exit

# Exit from OpenLANE flow docker sub-system
exit
```

</details>
<details>
	<summary> Day 3</summary>
	<br>

 ### Section 3 - Design Library Cell using Magic Layout and ngspice Characterization

#### Theory
Implementation details for creating, extracting, and simulating a custom inverter standard cell design using Magic and ngspice.

---

### Section 3 Tasks:

- **Clone Custom Inverter Standard Cell Design from GitHub Repository**
- **Load the Custom Inverter Layout in Magic and Explore**
- **SPICE Extraction of Inverter in Magic**
- **Editing the SPICE Model File for Analysis Through Simulation**
- **Post-layout ngspice Simulations**
- **Identify and Fix Issues in DRC Section of Old Magic Tech File**

---

#### 1. Clone Custom Inverter Standard Cell Design from GitHub Repository
```
# Change directory to OpenLANE working directory
cd Desktop/work/tools/openlane_working_dir/openlane

# Clone the repository with custom inverter design
git clone https://github.com/nickson-jose/vsdstdcelldesign

# Change into the cloned directory
cd vsdstdcelldesign

# Copy Magic tech file to the current directory
cp /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech .

# Check directory contents
ls

# Open custom inverter layout in Magic
magic -T sky130A.tech sky130_inv.mag &
```

**Screenshot of Commands Run**  
- Screenshot of terminal after cloning, navigating, and opening Magic.
![16](https://github.com/user-attachments/assets/d1e7544f-8342-41c3-a346-1637ba6b78af)

---

#### 2. Load the Custom Inverter Layout in Magic and Explore

**Screenshot of Inverter Layout Loaded in Magic**  
![17](https://github.com/user-attachments/assets/1fa03241-891c-4d5b-bc5a-10b8cc452a9f)

- **NMOS and PMOS Identified**
![18](https://github.com/user-attachments/assets/c5380bf8-2be7-486a-98fc-f5bdcf34a0cd)

![19](https://github.com/user-attachments/assets/36f863b1-005f-43eb-a566-7952ecdfb855)

- **Output Y Connectivity to PMOS and NMOS Drain Verified**
![20](https://github.com/user-attachments/assets/9ddb688e-ca19-4578-8b47-1099d553450d)


- **PMOS Source Connected to VDD (VPWR)**
![image](https://github.com/user-attachments/assets/1ce6dd7c-2d9e-4c04-be52-40bce62901f6)

- **NMOS Source Connected to VSS (VGND)**
![22](https://github.com/user-attachments/assets/4481752c-0508-409a-939f-2ed7915b88ba)

- **Deleting Layout Section to Test DRC Errors**

---

#### 3. SPICE Extraction of Inverter in Magic
Commands for SPICE extraction in the tkcon window:
```
# Verify current directory
pwd

# Extract to .ext format
extract all

# Enable parasitic extraction
ext2spice cthresh 0 rthresh 0

# Convert .ext file to .spice file
ext2spice
```

**Screenshot of tkcon Window**  
- **SPICE File Generated**

---

#### 4. Editing the SPICE Model File for Simulation
- Measured unit distance in layout grid.
- Final edited SPICE file prepared for ngspice simulation.

**Screenshots of SPICE File Editing and Grid Measurement**  

---

#### 5. Post-layout ngspice Simulations
```
# Load SPICE file in ngspice for simulation
ngspice sky130_inv.spice

# Plotting output waveform
plot y vs time a
```

**Screenshots of ngspice Run and Generated Plot**  
- **Rise and Fall Transition Time Calculation**:
  - Rise Transition Time = 63.96 ps
  - Fall Transition Time = 41.9 ps
- **Cell Delay Calculations**:
  - Rise Cell Delay = 61.36 ps
  - Fall Cell Delay = 20 ps

---

#### 6. Identify and Fix Issues in DRC Section of Old Magic Tech File

- Link to Sky130 Periphery Rules: [Skywater PDK Documentation](https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html)

```
# Change to home directory
cd

# Download and extract lab files
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
tar xfz drc_tests.tgz

# Navigate to extracted directory
cd drc_tests

# View .magicrc file
gvim .magicrc

# Open Magic tool with better graphics
magic -d XR &
```

**Screenshots of Commands Run and Corrected DRC Rules**  
- **Incorrectly Implemented poly.9, difftap.2, and nwell.4 Rules**:
  - Loaded updated `sky130A.tech` file.
  - Verified corrections using `drc check` and `drc why` commands.

- **Commands in tkcon Window**:
  ```
  tech load sky130A.tech
  drc check
  drc why
  ```
- **Screenshots of Magic with Corrected DRC Implementations**
![23](https://github.com/user-attachments/assets/cba3ef20-92db-4bdb-92d6-e198da3ddef1)
# 3. Spice Extraction of Inverter in Magic

## Commands for Spice Extraction in Magic
Below are the commands used in the `tkcon` window of Magic to extract the SPICE netlist from the custom inverter layout.

```
# Step 1: Check the current directory
pwd

# Step 2: Extraction command to generate .ext format
extract all

# Step 3: Enable parasitic extraction before converting to SPICE
ext2spice cthresh 0 rthresh 0

# Step 4: Convert the extracted .ext file to a SPICE file
ext2spice
```

### Screenshots
- **tkcon window after running the extraction commands:**
![24](https://github.com/user-attachments/assets/bd21aca6-1210-4488-b901-b5432e726e64)

- **Generated SPICE file:**
![25](https://github.com/user-attachments/assets/f38339c4-c70b-498b-992e-4a896dd822ed)

---

# 4. Editing the SPICE Model File for Simulation

### Additional Steps for SPICE Model Editing
Once the SPICE file is extracted, further modifications are required to prepare it for simulation with `ngspice`.

**Measuring the unit distance in the layout grid:**
![27](https://github.com/user-attachments/assets/2d99b281-7aca-416d-b068-281e0c63e32c)


**Final edited SPICE file ready for simulation:**
![28](https://github.com/user-attachments/assets/f88be0b4-9951-40a2-b66e-2bcb72e10e10)


---

These steps cover the process of extracting a SPICE netlist from a custom layout in Magic, including enabling parasitic extraction and editing the SPICE model for accurate simulation results.


### 5. Post-Layout ngspice Simulations

#### Commands for ngspice Simulation
The following commands are used to load and run the post-layout simulations using `ngspice`:
```
# Load the SPICE file for simulation
ngspice sky130_man.spice

# After entering ngspice, plot the required signals
plot y vs time a
```

#### Simulation Screenshots

Below are screenshots taken during the ngspice simulation run:

- Loading and running the simulation:
![29](https://github.com/user-attachments/assets/2175e0a4-8a13-4346-a2ee-864dd480ace0)

- Plotting the output waveform:
![30](https://github.com/user-attachments/assets/d5217ae9-edd9-4849-9db8-78bbb8a1a38c)
![31](https://github.com/user-attachments/assets/f01b2087-e04e-4498-ab7b-6722d0d63e35)

### Transition Time Calculations

#### Rise Transition Time
The rise transition time is calculated as:
Rise Transition Time = Time to reach 80% - Time to reach 20%
- 20% of output = 660 mV
- 80% of output = 2.64 V

Screenshots:
- For 20% transition:
![32](https://github.com/user-attachments/assets/ea90f668-4906-4f01-b059-685436a2975d)
![33](https://github.com/user-attachments/assets/847b2c7b-632a-45be-b87d-d914ec980fe2)

- For 80% transition:
![34](https://github.com/user-attachments/assets/a980a559-0567-4297-ba91-578d72132abe)
![35](https://github.com/user-attachments/assets/b9a62fa4-1243-444f-b30e-b4c60ae99b6f)

Calculation:
Rise Transition Time = 2.24638 ns - 2.18242 ns = 0.06396 ns = 63.96 ps

#### Fall Transition Time
The fall transition time is calculated as:
Fall Transition Time = Time to fall to 20% - Time to fall to 80%
- 20% of output = 660 mV
- 80% of output = 2.64 V

Screenshots:
- For 20% transition:
![39_20%](https://github.com/user-attachments/assets/911c949d-a6e1-4660-8a8c-b58ede9984dd)
![40](https://github.com/user-attachments/assets/5138f8ee-3c2c-4d63-8fae-ef18ce43bfad)

- For 80% transition:
![41](https://github.com/user-attachments/assets/774ff292-f7b1-4356-af0e-0f05e8e326cf)
![42](https://github.com/user-attachments/assets/99cc9975-a092-4c86-85f4-d133c4076840)


Calculation:
Fall Transition Time = 4.0955 ns - 4.0536 ns = 0.0419 ns = 41.9 ps

### Cell Delay Calculations

#### Rise Cell Delay
The rise cell delay is calculated as:
Rise Cell Delay = Time for output to reach 50% - Time for input to fall to 50%
- 50% of 3.3 V = 1.65 V

Screenshots:
![36](https://github.com/user-attachments/assets/f593b8e5-98e1-4306-a5be-f78d8505ac68)
![37](https://github.com/user-attachments/assets/e4d8f91d-589f-44d9-8863-27657e2e54fa)


Calculation:
Rise Cell Delay = 2.21144 ns - 2.15008 ns = 0.06136 ns = 61.36 ps

#### Fall Cell Delay
The fall cell delay is calculated as:
Fall Cell Delay = Time for output to fall to 50% - Time for input to rise to 50%
- 50% of 3.3 V = 1.65 V

Screenshots:
![43](https://github.com/user-attachments/assets/3a34b100-2e01-4261-9928-17fd8cff503c)
![44](https://github.com/user-attachments/assets/1d427821-c10f-4659-8964-367c81f14276)


Calculation:
Fall Cell Delay = 4.07 ns - 4.05 ns = 0.02 ns = 20 ps

These results highlight the performance metrics for the rise and fall transitions, as well as the cell delays, which are crucial for evaluating the timing behavior of the post-layout design.
# 6. DRC Correction in Magic for Skywater Process

## Objective
Fix issues in the DRC (Design Rule Check) section of the old Magic tech file for the Skywater process using the periphery rules found [here](https://skywater-pdk.readthedocs.io/en/main/rules/periphery.html).

---

## Step 1: Downloading and Viewing the Corrupted Skywater Process Files

### Commands
```
# Change to home directory
cd

# Download the lab files for DRC correction
wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz

# Extract the compressed lab files
tar xfz drc_tests.tgz

# Navigate into the extracted lab folder
cd drc_tests

# List all files and directories in the current directory
ls -al

# Open the .magicrc file for editing
gvim .magicrc

# Open Magic tool with better graphics mode
magic -d XR &
```

### Screenshots of Commands Run
![45](https://github.com/user-attachments/assets/2622c05d-3fe4-4780-a470-73f9cd3710c2)
![46](https://github.com/user-attachments/assets/0aa11903-e094-4a82-93ba-b820243f3fa8)

### Screenshot of `.magicrc` File

![47](https://github.com/user-attachments/assets/21f6b2e3-ed46-41c7-8cae-90fc2fb5c5d3)

---

## Step 2: Fixing Incorrectly Implemented DRC Rules

### Issue 1: Incorrect `poly.9` Rule
- The `poly.9` rule was incorrectly implemented, allowing spacing violations below 0.48μm.

**Correction Procedure:**
- Reviewed the `poly.9` rule, identified the issue, and updated the `sky130A.tech` file.

**Screenshots:**
- Poly rules correction
  ![48](https://github.com/user-attachments/assets/b052ec9e-8b44-4143-a465-0c8f3df718ae)
 ![49](https://github.com/user-attachments/assets/022ec87e-331e-48f1-9d04-ac6cc5cb3031)

- Violations before fix

**Updated DRC Commands in `tkcon` Window:**
```
# Load the updated tech file
tech load sky130A.tech

# Run the DRC check with updated rules
drc check

# Get error messages for the new violations
drc why
```

**Screenshots of Magic Window:**
![51](https://github.com/user-attachments/assets/ae11c354-4f30-42ee-8208-d67fb5d677e4)


---

### Issue 2: Incorrect `difftap.2` Rule
- The `difftap.2` rule was not properly checking spacing violations below 0.42μm.
**Correction Procedure:**
- Reviewed and updated the `difftap.2` rule in the `sky130A.tech` file.
![50](https://github.com/user-attachments/assets/c04dfbc2-ea4d-477b-bbd0-05d49a6a5ffa)

**Screenshots:**
![54](https://github.com/user-attachments/assets/b986355d-30c3-4901-9efd-8862989a1393)
**Updated DRC Commands in `tkcon` Window:**
```
# Load the updated tech file
tech load sky130A.tech

# Run the DRC check with updated rules
drc check

# Get error messages for the new violations
drc why
```

---

### Issue 3: Incorrect `nwell.4` Rule
- The `nwell.4` rule was not identifying violations when no tap was present within the nwell region.

**Correction Procedure:**
- Fixed the implementation of the `nwell.4` rule and updated the `sky130A.tech` file.
- Nwell rules correction: 
- Violations before fix: 


**Updated DRC Commands in `tkcon` Window:**
```
# Load the updated tech file
tech load sky130A.tech

# Switch to full DRC check mode
drc style drc(full)

# Re-run the DRC check
drc check

# Get error messages for the new violations
drc why
```

**Screenshot of Magic Window:**
![55](https://github.com/user-attachments/assets/64e60ae4-87df-48e6-bf12-fc58340be35a)
![57](https://github.com/user-attachments/assets/dee2ac75-7eb6-4a05-8920-87755e772b01)
![56](https://github.com/user-attachments/assets/cfe8537a-508c-4ad9-bef1-f2ecfdbfbeee)

---

## Summary
The above steps detail how to download the old Skywater process tech files, identify issues in the DRC rules, correct the faulty rules, and validate the corrections using Magic's DRC commands. These fixes ensure adherence to the Sky130 periphery rules.


</details>
<details>
	<summary> Day 4</summary>
	<br>

 ### Section 4 - Pre-layout timing analysis and importance of good clock tree (22/03/2024 - 24/03/2024)

**Theory**  
Implementation

---

### Section 4 tasks:
- Fix up small DRC errors and verify the design is ready to be inserted into our flow.
- Save the finalized layout with custom name and open it.
- Generate LEF from the layout.
- Copy the newly generated LEF and associated required lib files to `picorv32a` design `src` directory.
- Edit `config.tcl` to change lib file and add the new extra LEF into the OpenLane flow.
- Run OpenLane flow synthesis with newly inserted custom inverter cell.
- Remove/reduce the newly introduced violations with the introduction of custom inverter cell by modifying design parameters.
- Once synthesis has accepted our custom inverter, run floorplan and placement, and verify the cell is accepted in PnR flow.
- Perform Post-Synthesis timing analysis with OpenSTA tool.
- Make timing ECO fixes to remove all violations.
- Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement, and CTS.
- Post-CTS OpenROAD timing analysis.
- Explore post-CTS OpenROAD timing analysis by removing `sky130_fd_sc_hd__clkbuf_1` cell from clock buffer list variable `CTS_CLK_BUFFER_LIST`.

---
### Commands and Procedures

```bash
# Step 1: Fix up small DRC errors
# Conditions to verify before moving forward with custom designed cell layout:
# Condition 1: The input and output ports of the standard cell should lie on the intersection of the vertical and horizontal tracks.
# Condition 2: Width of the standard cell should be odd multiples of the horizontal track pitch.
# Condition 3: Height of the standard cell should be even multiples of the vertical track pitch.

# Open the custom inverter layout
```
```
cd Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign
magic -T sky130A.tech sky130_man.mag &
```

# Commands for tkcon window to set grid as tracks of locali layer
```
help grid
grid 0.46um 0.34um 0.23um 0.17um
```
![59](https://github.com/user-attachments/assets/d45e2872-ba91-4bc3-b721-a53cbb998de3)
Condition 1 verified
![60](https://github.com/user-attachments/assets/291f465f-4db4-495d-9f7d-ce8346da6679)
Condition 2 verified
		Horizontal track pitch = 0.46um
![61](https://github.com/user-attachments/assets/80d85ba7-e784-4f51-8d10-af30100df0c9)
		width of standard cell = 1.38um
Condition 3 verified
		vertical track pitch = 0.34um
![62](https://github.com/user-attachments/assets/62d07146-7750-467e-91e4-871b6f12f147)
		Height of standardcell = 2.72um

# Step 2: Save the finalized layout with custom name and open it
```
save sky130_man.mag
magic -T sky130A.tech sky130_man.mag &
```
# Step 3: Generate LEF from the layout
```
lef write
```
![63](https://github.com/user-attachments/assets/442085ee-d009-4542-a4fb-ddbef8bb63b9)

Screenshot of newly created lef file:
![64](https://github.com/user-attachments/assets/bd266eff-8e23-4575-8853-a1066aaee6fa)

# Step 4: Copy the newly generated LEF and lib files to 'picorv32a' design 'src' directory
```
cp sky130_man.lef ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
ls ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
cp libs/sky130_fd_sc_hd__* ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/
```
![65](https://github.com/user-attachments/assets/0681c0c0-70be-4895-988e-4c37987a11fb)

# Step 5: Edit 'config.tcl' to change lib file and add the new extra LEF
```
set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]
```

# Step 6: Run OpenLane flow synthesis with newly inserted custom inverter cell
```
cd Desktop/work/tools/openlane_working_dir/openlane
docker
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs
run_synthesis
```
![66](https://github.com/user-attachments/assets/2adbf295-f441-4a67-97e9-6f7af56c84b3)
![67](https://github.com/user-attachments/assets/6fa7982b-73b1-4d9f-9859-4a8f87dee163)
![68](https://github.com/user-attachments/assets/be5eb0bc-51b2-4f1c-8089-dc6c978221e1)

# Step 7: Remove/reduce the newly introduced violations
```
prep -design picorv32a -tag 14-11_12-03 -overwrite
set ::env(SYNTH_SIZING) 1
run_synthesis
```
![69](https://github.com/user-attachments/assets/418172c3-a2a6-461e-882a-04d2a1ccc7be)
![70](https://github.com/user-attachments/assets/585a4509-2391-45dc-afc1-83d89fdc1dd5)
![71](https://github.com/user-attachments/assets/ed3238d6-ea8f-46d8-b550-e97a717d0ffa)
![72](https://github.com/user-attachments/assets/b1612acd-59ce-4fc8-a1b5-02390a190c8b)

# Step 8: Once synthesis has accepted the custom inverter, run floorplan and placement
```
run_floorplan
run_placement
```
![74](https://github.com/user-attachments/assets/b583d124-21d0-425f-b091-cd93914e8bd3)
![75](https://github.com/user-attachments/assets/3036c5a8-4f42-49dc-9e5b-6d2d948896c7)
![76](https://github.com/user-attachments/assets/db71553f-4ed0-44a7-be29-3fc40a22b16f)
```
# Follwing commands are alltogather sourced in "run_floorplan" command
init_floorplan
place_io
tap_decap_or
```
![77](https://github.com/user-attachments/assets/998f33bd-913d-4c4b-b169-140791612781)
![78](https://github.com/user-attachments/assets/edc09227-406b-4387-8732-c253b8b3b4b7)
![79](https://github.com/user-attachments/assets/a77ece86-279b-40c1-902b-5c778f1cbc99)

## Commands to load placement def in magic in another terminal
```
# Change directory to path containing generated placement def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/14-11_12-03/results/placement/

# Command to load the placement def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```
![81](https://github.com/user-attachments/assets/72ea7710-6784-4c6a-9d52-2d807b08e8b6)
![82](https://github.com/user-attachments/assets/d7e5bb32-5fc8-41aa-8374-d76096938f14)
![inverter_name](https://github.com/user-attachments/assets/fd19d2d3-0e67-4a03-b79e-eacbeb08b61b)

# Step 9: Perform Post-Synthesis timing analysis with OpenSTA
```
cd Desktop/work/tools/openlane_working_dir/openlane
docker
./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a
add_lefs -src $lefs
set ::env(SYNTH_SIZING) 1
run_synthesis
sta pre_sta.conf
```
![83](https://github.com/user-attachments/assets/eba7c236-36e8-4261-8977-f195810b0ba7)
![84](https://github.com/user-attachments/assets/bbc8e226-d97b-4c68-8b33-cdf2b861502e)
![85](https://github.com/user-attachments/assets/b1530241-623b-40d6-8f09-49acc4e4cc15)
![86](https://github.com/user-attachments/assets/b989135e-4e7f-4a03-afdd-1db9875365c2)
![87](https://github.com/user-attachments/assets/6e6375e2-d58c-4c28-8981-f1aab9218be3)
![88](https://github.com/user-attachments/assets/df174c6a-d004-4ed3-b9a7-2b6dbc55c33a)
![89](https://github.com/user-attachments/assets/b0d8b850-1574-4afb-8ccb-1e96ec490297)
![91](https://github.com/user-attachments/assets/2c892cf3-8f4d-4222-ac59-f23b9903a31c)

# Step 10: Make timing ECO fixes
```
prep -design picorv32a -tag 25-03_18-52 -overwrite
set ::env(SYNTH_SIZING) 1
set ::env(SYNTH_MAX_FANOUT) 4
run_synthesis
```
reducing the slack:
![93](https://github.com/user-attachments/assets/4dbaaf50-b4e6-4362-b244-a0c6cc6d8b5e)
OR gate of drive strength 2 is driving 4 fanouts
![94](https://github.com/user-attachments/assets/e57954a7-cbfa-4ab4-a487-714808dcfebe)
Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
```
# Reports all the connections to a net
report_net -connections _11672_

# Checking command syntax
help replace_cell

# Replacing cell
replace_cell _14510_ sky130_fd_sc_hd__or3_4

# Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
```
Result - slack reduced
![95](https://github.com/user-attachments/assets/a488f134-88f3-4847-972d-d0974cd1fb11)
OR gate of drive strength 2 is driving 4 fanouts
![96](https://github.com/user-attachments/assets/16ab086c-dd4f-4729-9982-ef453ec54cf5)
Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
```
# Reports all the connections to a net
report_net -connections _11675_

# Replacing cell
replace_cell _14514_ sky130_fd_sc_hd__or3_4

# Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
```
Result - slack reduced
![97](https://github.com/user-attachments/assets/2073f709-f895-498f-8ad7-74291b66dac0)
OR gate of drive strength 2 driving OA gate has more delay
![98](https://github.com/user-attachments/assets/7d68373f-19fa-4298-8b0d-bb7484db151e)
Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
```
# Reports all the connections to a net
report_net -connections _11643_

# Replacing cell
replace_cell _14481_ sky130_fd_sc_hd__or4_4

# Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
```
Result - slack reduced
![99](https://github.com/user-attachments/assets/9e48d8cc-7cca-47a3-8542-966c13890b0d)
OR gate of drive strength 2 driving OA gate has more delay
![100](https://github.com/user-attachments/assets/29002609-95d9-4fb7-ad54-f99bb9ce0d79)
Commands to perform analysis and optimize timing by replacing with OR gate of drive strength 4
```
# Reports all the connections to a net
report_net -connections _11668_

# Replacing cell
replace_cell _14506_ sky130_fd_sc_hd__or4_4

# Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
```
Result - slack reduced
![101](https://github.com/user-attachments/assets/66344c7e-e855-47e8-8058-0cbc408adee3)
Commands to verify instance _14506_ is replaced with sky130_fd_sc_hd__or4_4
```
# Generating custom timing report
report_checks -from _29043_ -to _30440_ -through _14506_
```
![102](https://github.com/user-attachments/assets/1a0bc647-d277-4703-bca9-222cd80eb4b2)
## 11. Replace the old netlist with the new netlist generated after timing ECO fix and implement the floorplan, placement and cts.
Now to insert this updated netlist to PnR flow and we can use write_verilog and overwrite the synthesis netlist but before that we are going to make a copy of the old old netlist

Commands to make copy of netlist
```
# Change from home directory to synthesis results directory
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/25-03_18-52/results/synthesis/

# List contents of the directory
ls

# Copy and rename the netlist
cp picorv32a.synthesis.v picorv32a.synthesis_old.v

# List contents of the directory
ls
```
Screenshot of commands run
![103](https://github.com/user-attachments/assets/d4343052-a617-4913-b1f6-2ba7c9d0ac5e)
Commands to write verilog
```
# Check syntax
help write_verilog

# Overwriting current synthesis netlist
write_verilog /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/14-11_12-03/results/synthesis/picorv32a.synthesis.v

# Exit from OpenSTA since timing analysis is done
exit
```
Since we confirmed that netlist is replaced and will be loaded in PnR but since we want to follow up on the earlier 0 violation design we are continuing with the clean design to further stages

Commands load the design and run necessary stages
```
# Now once again we have to prep design so as to update variables
prep -design picorv32a -tag 24-03_10-03 -overwrite

# Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

# Follwing commands are alltogather sourced in "run_floorplan" command
init_floorplan
place_io
tap_decap_or

# Now we are ready to run placement
run_placement

# Incase getting error
unset ::env(LIB_CTS)

# With placement done we are now ready to run CTS
run_cts
```
![104](https://github.com/user-attachments/assets/219142e8-ad8a-4de9-a573-a98555bceea6)
![105](https://github.com/user-attachments/assets/11c9e358-f0ea-4c63-8dfe-347d86254ca9)
![106](https://github.com/user-attachments/assets/2fbfeb95-8a30-4958-9042-2ff56bf5899d)
![107](https://github.com/user-attachments/assets/3f2be069-0afd-4822-ac18-c5470bdbb11f)
![108](https://github.com/user-attachments/assets/bd212c69-3090-43b1-96ca-13abe0da8331)
![109](https://github.com/user-attachments/assets/ab770d1f-9b2c-4f13-8212-93ba390be2c4)
![110](https://github.com/user-attachments/assets/ff762129-9c56-4bad-a1f2-71cf8c20e43e)

## 12. Post-CTS OpenROAD timing analysis.
Commands to be run in OpenLANE flow to do OpenROAD timing analysis with integrated OpenSTA in OpenROAD
```
# Command to run OpenROAD tool
openroad

# Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/14-11_12-03/tmp/merged.lef

# Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/14-11_12-03/results/cts/picorv32a.cts.def

# Creating an OpenROAD database to work with
write_db pico_cts.db

# Loading the created database in OpenROAD
read_db pico_cts.db

# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/14-11_12-03/results/synthesis/picorv32a.synthesis_cts.v

# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link design and library
link_design picorv32a

# Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

# Check syntax of 'report_checks' command
help report_checks

# Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Exit to OpenLANE flow
exit
```
Screenshots of commands run and timing report generated
![111](https://github.com/user-attachments/assets/f3bfb491-e6a1-434e-9fbb-ac38154b3644)
![112](https://github.com/user-attachments/assets/65f5b467-5326-4b69-b50d-14bd68af89a8)
![113](https://github.com/user-attachments/assets/1f53da87-a947-489a-8fdd-2bb03dacdfc5)
![114](https://github.com/user-attachments/assets/3620b7e9-8f6a-4620-9bbf-8c3d86e24108)

## 13. Explore post-CTS OpenROAD timing analysis by removing 'sky130_fd_sc_hd__clkbuf_1' cell from clock buffer list variable 'CTS_CLK_BUFFER_LIST'.
Commands to be run in OpenLANE flow to do OpenROAD timing analysis after changing CTS_CLK_BUFFER_LIST
```
# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Removing 'sky130_fd_sc_hd__clkbuf_1' from the list
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Checking current value of 'CURRENT_DEF'
echo $::env(CURRENT_DEF)

# Setting def as placement def
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/placement/picorv32a.placement.def

# Run CTS again
run_cts

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Command to run OpenROAD tool
openroad

# Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/24-03_10-03/tmp/merged.lef

# Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/cts/picorv32a.cts.def

# Creating an OpenROAD database to work with
write_db pico_cts1.db

# Loading the created database in OpenROAD
read_db pico_cts.db

# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/24-03_10-03/results/synthesis/picorv32a.synthesis_cts.v

# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link design and library
link_design picorv32a

# Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

# Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Report hold skew
report_clock_skew -hold

# Report setup skew
report_clock_skew -setup

# Exit to OpenLANE flow
exit

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Inserting 'sky130_fd_sc_hd__clkbuf_1' to first index of list
set ::env(CTS_CLK_BUFFER_LIST) [linsert $::env(CTS_CLK_BUFFER_LIST) 0 sky130_fd_sc_hd__clkbuf_1]

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)
```
Screenshots of commands run and timing report generated
![115](https://github.com/user-attachments/assets/9d64b395-cab7-42f1-b0e0-901914e37bf7)
![116](https://github.com/user-attachments/assets/2fb38ed4-c299-4224-85ab-bbffbba454bc)
![117](https://github.com/user-attachments/assets/deca02e6-d004-4677-8a09-79088cc77654)
![118](https://github.com/user-attachments/assets/3ef4330b-9b7d-4a72-8ace-1d539de64f36)

</details>
<details>
	<summary> Day 5</summary>
	<br>

# Section 5 - Final steps for RTL2GDS using tritonRoute and openSTA
## Theory
## Implementation
## Section 5 tasks:-
Perform generation of Power Distribution Network (PDN) and explore the PDN layout.
Perfrom detailed routing using TritonRoute.
Post-Route parasitic extraction using SPEF extractor.
Post-Route OpenSTA timing analysis with the extracted parasitics of the route.
1. Perform generation of Power Distribution Network (PDN) and explore the PDN layout.
Commands to perform all necessary stages up until now
```
# Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
# Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
```
```
# Now that we have entered the OpenLANE flow contained docker sub-system we can invoke the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

# Now that OpenLANE flow is open we have to input the required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a

# Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

# Following commands are alltogather sourced in "run_floorplan" command
init_floorplan
place_io
tap_decap_or

# Now we are ready to run placement
run_placement

# Incase getting error
unset ::env(LIB_CTS)

# With placement done we are now ready to run CTS
run_cts

# Now that CTS is done we can do power distribution network
gen_pdn
```
Screenshots of power distribution network run
![119](https://github.com/user-attachments/assets/78a9b047-b98a-4d34-9f81-e5c2ad25434b)
![120](https://github.com/user-attachments/assets/83bd72b9-44d5-46a1-9166-2ebcaad0a235)
![121](https://github.com/user-attachments/assets/3d638760-e8dc-4e3f-9509-b0ce1db94460)
![122](https://github.com/user-attachments/assets/8a1f2752-3a11-4c79-8272-be8e67c49e79)
![123](https://github.com/user-attachments/assets/abf817f8-69f0-4c87-ab43-27aae567f1b0)
![124](https://github.com/user-attachments/assets/d8eb112f-e617-4d88-9938-a185a577f8b1)
![125](https://github.com/user-attachments/assets/4124803b-eca7-4d1f-b219-225a3971b04c)
![126](https://github.com/user-attachments/assets/eaf6855a-d462-48b9-9be1-5390e289fe8d)
![127](https://github.com/user-attachments/assets/5383d958-75a0-4a82-a623-11ca875c1a09)
## Commands to load PDN def in magic in another terminal
```
# Change directory to path containing generated PDN def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/14-11_15-23/tmp/floorplan/

# Command to load the PDN def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read 14-pdn.def &
```
## Screenshots of PDN def
![128](https://github.com/user-attachments/assets/7e240119-22f6-494e-9b4c-e9956fe02b0e)
![129](https://github.com/user-attachments/assets/f489f4e4-ea85-49ba-9c2a-eb5737a185a1)
![130](https://github.com/user-attachments/assets/efa97850-bd6f-4138-8e07-5e934097f12b)
## 2. Perfrom detailed routing using TritonRoute and explore the routed layout.
Command to perform routing
```
# Check value of 'CURRENT_DEF'
echo $::env(CURRENT_DEF)

# Check value of 'ROUTING_STRATEGY'
echo $::env(ROUTING_STRATEGY)

# Command for detailed route using TritonRoute
run_routing
```
Screenshots of routing run:
![131](https://github.com/user-attachments/assets/acdcb0cd-84dc-4b48-8956-bc3f721fb24f)
![132](https://github.com/user-attachments/assets/a8f753e9-c458-4c3e-9c80-39c9c6ccb17e)
![133](https://github.com/user-attachments/assets/37d7329b-f9c2-45d9-8f3e-24457dfb2e77)
Commands to load routed def in magic in another terminal
```
# Change directory to path containing routed def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/14-11_15-23/results/routing/

# Command to load the routed def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.def &
```
![134](https://github.com/user-attachments/assets/f2416dee-6887-42ae-814c-2c2df8281d48)
![135](https://github.com/user-attachments/assets/4cdc947c-df1d-4e4f-a619-6e98a7a54a69)
Screenshot of fast route guide present in openlane/designs/picorv32a/runs/14-11_15-23/tmp/routing directory
![138](https://github.com/user-attachments/assets/1a57a846-eeca-449c-8223-5f05e73e0111)
## 3. Post-Route parasitic extraction using SPEF extractor.
Commands for SPEF extraction using external tool
```
# Change directory
cd Desktop/work/tools/SPEF_EXTRACTOR

# Command extract spef
python3 main.py /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/26-03_08-45/tmp/merged.lef /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/26-03_08-45/results/routing/picorv32a.def
```
## 4. Post-Route OpenSTA timing analysis with the extracted parasitics of the route.
Commands to be run in OpenLANE flow to do OpenROAD timing analysis with integrated OpenSTA in OpenROAD
```
# Command to run OpenROAD tool
openroad

# Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/26-03_08-45/tmp/merged.lef

# Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/26-03_08-45/results/routing/picorv32a.def

# Creating an OpenROAD database to work with
write_db pico_route.db

# Loading the created database in OpenROAD
read_db pico_route.db

# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/26-03_08-45/results/synthesis/picorv32a.synthesis_preroute.v

# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link design and library
link_design picorv32a

# Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

# Read SPEF
read_spef /openLANE_flow/designs/picorv32a/runs/26-03_08-45/results/routing/picorv32a.spef

# Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Exit to OpenLANE flow
exit
```
Screenshots of commands run and timing report generated
![139](https://github.com/user-attachments/assets/8925bf2e-8405-4f75-ba5f-d3383a1fb417)
![140](https://github.com/user-attachments/assets/5f20add3-cbc9-427b-bfde-bc3a5114dfd4)

</details>
</details>
<details>
	<summary>ASIC Lab 13</summary>
	<br>

 # Installing and Setting Up ORFS  
```
git clone --recursive https://github.com/The-OpenROAD-Project/OpenROAD-flow-scripts .  
cd OpenRoad  
sudo ./setup.sh  
./build_openroad.sh --local  
```
![Screenshot from 2024-11-25 23-46-41](https://github.com/user-attachments/assets/4be65a2e-0c62-4c43-8c37-23d2a60ed85b)
![Screenshot from 2024-11-25 23-56-11](https://github.com/user-attachments/assets/bc269884-487d-4a28-b325-c86e80494dda)

# Verify Installation  
```
source ./env.sh  
yosys -help  
openroad -help  
cd flow  
make  
```
![Screenshot from 2024-11-26 00-01-22](https://github.com/user-attachments/assets/3279eeb5-cc44-4a5f-8fb8-4199cbbc65e1)
![Screenshot from 2024-11-26 00-01-39](https://github.com/user-attachments/assets/df354a15-1c6c-4618-868d-cf8abd96e695)
![Screenshot from 2024-11-26 00-02-34](https://github.com/user-attachments/assets/cceede71-e204-44d6-8eab-15bdb6669d33)

# Expected Output: 1. Successful execution of `make`.  
# To view the final GUI:  
```
make gui_final  
```
![Screenshot from 2024-11-26 00-02-48](https://github.com/user-attachments/assets/ec58a99f-990c-429d-9531-fa2453d0e045)

# Expected Output: 2. OpenROAD GUI opens with the design loaded.  

### ORFS Directory Structure and File Formats  
### `OpenROAD-flow-scripts` Directory:  
### - `docker`: Contains Docker installation scripts and related files.  
### - `docs`: Documentation for OpenROAD tools and flow scripts.  
### - `flow`: Files to run the RTL-to-GDS flow.  
### - `jenkins`: Regression tests for each build update.  
### - `tools`: All tools required for RTL-to-GDS flow.  
### - `etc`: Dependency installer scripts and other related files.  
### - `setup_env.sh`: Source file to set up OpenROAD rules for RTL-to-GDS flow.  

### Navigate to the `flow` Directory:  
### - `design`: Contains built-in RTL-to-GDS flow examples for various technology nodes.  
### - `makefile`: Automates the flow setup.  
### - `platform`: Libraries, LEF files, GDS, and more for different technology nodes.  
### - `tutorials`: Tutorial resources.  
### - `util`: Utility scripts and files.  
### - `scripts`: Custom scripts used in the flow.  

### Automated RTL-to-GDS Flow for VSDBabySoC  

# Initial Setup:  
```
mkdir -p OpenROAD-flow-scripts/flow/designs/sky130hd/vsdbabysoc  
```
### Copy the following folders from the VSDBabySoC folder into this directory:  
### - `gds`: Contains `avsddac.gds` and `avsdpll.gds`.  
### - `include`: Includes header files like `sandpiper.vh`, `sandpiper_gen.vh`, etc.  
### - `lef`: Contains LEF files such as `avsddac.lef` and `avsdpll.lef`.  
### - `lib`: Library files such as `avsddac.lib` and `avsdpll.lib`.  
### Copy the constraints file `vsdbabysoc_synthesis.sdc` into the directory.  
### Copy the files `macro.cfg` and `pin_order.cfg` into the directory.  

# Setup Environment:  
```
cd OpenRoad  
source env.sh  
cd flow  
```
![Screenshot from 2024-11-26 00-18-05](https://github.com/user-attachments/assets/1cd97a41-472d-4391-abfb-f9b5d25f5d53)

# Commands for Synthesis:  
```
make DESIGN_CONFIG=./designs/sky130hd/vsdbabysoc/config.mk synth  
```
![Screenshot from 2024-11-26 00-18-40](https://github.com/user-attachments/assets/08f3c1db-a1f8-4e27-a2bf-157395e72479)

### Expected Outputs:  
### 5. Synthesis netlist generated.  
### 6. Synthesis log available for review.  
### 7. Check synthesis results for correctness.  
### 8. Obtain synthesis statistics.  

### Commands for Floorplan:  
### Generate the floorplan:  
```
make DESIGN_CONFIG=./designs/sky130hd/vsdbabysoc/config.mk floorplan  
```
![Screenshot from 2024-11-26 00-19-35](https://github.com/user-attachments/assets/5ecaa319-8b03-4fa7-adc4-a794a933e826)

# View the floorplan in GUI:  
```
make gui_floorplan
```
![Screenshot from 2024-11-26 00-20-08](https://github.com/user-attachments/assets/ced304ff-748d-4d77-8f6d-1c9054404a76)
![Screenshot from 2024-11-26 00-20-37](https://github.com/user-attachments/assets/811b2a38-c736-4f87-9bc9-93b9a3e96d46)

```
make DESIGN_CONFIG=./designs/sky130hd/vsdbabysoc/config.mk gui_floorplan  
```
![Screenshot from 2024-11-26 00-21-51](https://github.com/user-attachments/assets/5f354a33-d36f-4eac-ae15-3d4f53a75ce3)
![Screenshot from 2024-11-26 00-22-51](https://github.com/user-attachments/assets/c387e71b-85cd-4707-ba7b-c10b1cefbf64)
![Screenshot from 2024-11-26 00-23-13](https://github.com/user-attachments/assets/e0f6ab3d-c119-46a8-9e95-e87f9639b069)
```
make DESIGN_CONFIG=./designs/sky130hd/vsdbabysoc/config.mk place
```
![Screenshot from 2024-11-26 00-23-57](https://github.com/user-attachments/assets/31de0cb9-a3cb-4375-9999-9fe6134b3e53)
![Screenshot from 2024-11-26 00-25-44](https://github.com/user-attachments/assets/fa0652bf-6fe6-47e8-a4d9-5325d101d97e)
![Screenshot from 2024-11-26 00-25-05](https://github.com/user-attachments/assets/3a37d042-921b-4e43-96b9-deb29248ca6d)
```
make DESIGN_CONFIG=./designs/sky130hd/vsdbabysoc/config.mk cts
```
![Screenshot from 2024-11-26 00-26-27](https://github.com/user-attachments/assets/496b341e-49dc-4c46-b175-be3acb434850)
```
make DESIGN_CONFIG=./designs/sky130hd/vsdbabysoc/config.mk route
```
![Screenshot from 2024-11-26 00-31-42](https://github.com/user-attachments/assets/85c1fff3-3d59-4d35-b069-11b5ae50981a)
![Screenshot from 2024-11-26 00-31-48](https://github.com/user-attachments/assets/fa2d936d-7408-4d52-9de8-f1baa8dc5719)

</details>
