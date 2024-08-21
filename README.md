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
<summary>ASIC Lab5</summary>
<br>

# Building a five stage pipelining RISC-V processor core #
This repository features a 5-stage pipelined RISC-V core built using TL-Verilog (Transactional Verilog). TL-Verilog enhances the design process by emphasizing data transactions and pipeline efficiency, making it ideal for creating scalable and modular hardware designs. This project demonstrates the implementation of a RISC-V core, highlighting the advantages of TL-Verilog in modern CPU design. Explore the code to see how TL-Verilog facilitates the construction of a pipelined architecture.
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
