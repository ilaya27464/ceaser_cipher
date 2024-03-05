# Ex.No: 01 IMPLEMENTATION OF CAESAR CIPHER
### DATE: 27-02-2024                                                                          
### REGISTER NUMBER : 212221040057
### AIM: 
To implement the simple substitution technique named Caesar cipher using C language.
### STEPS:
1. Read the plain text from the user.
2. Read the key value from the user.
3. If the key is positive then encrypt the text by adding the key with each character in the plain text.
4. Else subtract the key from the plain text.
5. Display the cipher text obtained above.

### PROGRAM:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

char ALPHABET[] = "abcdefghijklmnopqrstuvwxyz";

void encrypt(char* text, int shift) {
    for (int i = 0; text[i] != '\0'; i++) {
        if (isalpha(text[i])) {
            int index = tolower(text[i]) - 'a';
            text[i] = ALPHABET[(index + shift) % 26];
        }
    }
}

void decrypt(char* text, int shift) {
    encrypt(text, -shift);
}

int main() {
    char choice[10];
    char text[100];
    int shift;
    printf("Do you want to encrypt or decrypt? ");
    scanf("%s", choice);
    printf("Enter the text: ");
    scanf("%s", text);
    printf("Enter the shift: ");
    scanf("%d", &shift);

    if (strcmp(choice, "encrypt") == 0) {
        encrypt(text, shift);
        printf("Encrypted text: %s\n", text);
    } else if (strcmp(choice, "decrypt") == 0) {
        decrypt(text, shift);
        printf("Decrypted text: %s\n", text);
    } else {
        printf("Invalid choice.\n");
    }

    return 0;
}
```


### OUTPUT:

## Encryption:

## Decryption:


### RESULT:
Thus the implementation of Caesar cipher had been executed successfully.
