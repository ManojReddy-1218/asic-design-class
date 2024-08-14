# ASIC LAB 4 #
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
