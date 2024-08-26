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

# RISC-V Pre-Synthesis Simulation using Icarus Verilog, GTKWave, and Makerchip

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
