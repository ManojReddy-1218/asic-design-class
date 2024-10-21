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


</details>


</details>
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
</details>
</details>
