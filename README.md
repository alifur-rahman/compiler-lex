

# compiler-lex


Lex is a tool or a computer program that generates Lexical Analyzers (converts the stream of
characters into tokens). The Lex tool itself is a compiler. The Lex compiler takes the input and
transforms that input into input patterns. It is commonly used with YACC (Yet Another Compiler
Compiler).

<img src='https://github.com/alifur-rahman/compiler-lex/blob/main/Screenshot%202024-02-05%20114849.png'>


# The function of Lex:

1. In the first step the source code which is in the Lex language having the file name ‘File.l’
gives as input to the Lex Compiler commonly known as Lex to get the output as lex.yy.c
2. After that, the output lex.yy.c will be used as input to the C compiler which gives the
output in the form of an ‘a.out’ file, and finally, the output file a.out will take the stream
of character and generates tokens as output.

<img src='https://github.com/alifur-rahman/compiler-lex/blob/main/Screenshot%202024-02-05%20115408.png'>

# C Program to Check Keywords

## Overview

This C program allows the user to input a word and determines whether the entered word is a keyword in the C programming language. It utilizes a function to check for keywords and a main program loop to interactively receive user input.

## Keyword Detection Function

The `isKeyword` function checks if a given word is a C keyword. It takes a word as input and compares it against a predefined list of C keywords.




### code in C
```c

#include <stdio.h>
#include <string.h>

// Function to check if a given word is a keyword
int isKeyword(const char *word) {
    // List of keywords
    const char *keywords[] = {"if", "else", "while", "for", "int", "float", "return", "break", "continue",
                              "switch", "case", "char", "double", "enum", "extern", "long", "short",
                              "signed", "sizeof", "static", "struct", "typedef", "union", "void", "volatile"};

    // Calculate the number of keywords
    int numKeywords = sizeof(keywords) / sizeof(keywords[0]);

    // Check if the input word matches any keyword
    for (int i = 0; i < numKeywords; i++) {
        if (strcmp(word, keywords[i]) == 0) {
            return 1; // Keyword found
        }
    }

    return 0; // Keyword not found
}

int main() {
    char userInput[100];
    int exitProgram = 0;

    while (!exitProgram) {
        // Prompt the user for input
        printf("Enter a word (type 'exit' to end): ");
        scanf("%s", userInput);

        // Check if the user wants to exit
        if (strcmp(userInput, "exit") == 0) {
            printf("Exiting the program.\n");
            exitProgram = 1;
        } else {
            // Check if the input is a keyword
            if (isKeyword(userInput)) {
                printf("Keyword detected: %s\n", userInput);
                // Perform actions associated with the keyword here
            } else {
                printf("Input is not a keyword.\n");
            }
        }
    }

    return 0;
}

```
