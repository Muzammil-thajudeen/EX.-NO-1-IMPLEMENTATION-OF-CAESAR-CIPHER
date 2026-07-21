# EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER

## AIM:
To implement the simple substitution technique named Caesar cipher using C language.

## ALOGORITHM:

STEP-1: Read the plain text from the user.

STEP-2: Read the key value from the user.

STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.

STEP-4: Else subtract the key from the plain text.

STEP-5: Display the cipher text obtained above.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char text[100], cipher[100];
    int key, i;

    printf("Enter text: ");
    scanf("%99s", text);

    printf("Enter key: ");
    scanf("%d", &key);

    key %= 26;

    // Encryption
    for (i = 0; text[i] != '\0'; i++) {
        if (isupper(text[i]))
            cipher[i] = (text[i] - 'A' + key) % 26 + 'A';
        else if (islower(text[i]))
            cipher[i] = (text[i] - 'a' + key) % 26 + 'a';
        else
            cipher[i] = text[i];
    }
    cipher[i] = '\0';

    printf("\nEncrypted: %s", cipher);

    // Decryption
    for (i = 0; cipher[i] != '\0'; i++) {
        if (isupper(cipher[i]))
            text[i] = (cipher[i] - 'A' - key + 26) % 26 + 'A';
        else if (islower(cipher[i]))
            text[i] = (cipher[i] - 'a' - key + 26) % 26 + 'a';
        else
            text[i] = cipher[i];
    }
    text[i] = '\0';

    printf("\nDecrypted: %s\n", text);

    return 0;
}
```


## OUTPUT:
<img width="1797" height="842" alt="image" src="https://github.com/user-attachments/assets/65299f7b-b7b4-4b87-b64c-3c9eebfb8377" />


## RESULT :
 Thus the implementation of ceasar cipher had been executed successfully.
