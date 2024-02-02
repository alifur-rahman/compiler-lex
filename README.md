# compiler-lex

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
