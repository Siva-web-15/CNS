## EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER
## NAME: Sivabalan M
## REGISTER NO: 212224230269

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


PROGRAM :-
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char plain[100], cipher[100];
    int key, i, length;

    printf("\nEnter the plain text: ");
    scanf("%99s", plain); // Limiting input to prevent buffer overflow

    printf("\nEnter the key value: ");
    scanf("%d", &key);

    length = strlen(plain);

    printf("\n\n\tPLAIN TEXT: %s", plain);
    printf("\n\n\tENCRYPTED TEXT: ");

    for (i = 0; i < length; i++) {
        cipher[i] = plain[i] + key;

        // Adjust for uppercase letters
        if (isupper(plain[i]) && cipher[i] > 'Z') {
            cipher[i] -= 26;
        }
        // Adjust for lowercase letters
        if (islower(plain[i]) && cipher[i] > 'z') {
            cipher[i] -= 26;
        }

        printf("%c", cipher[i]);
    }
    cipher[length] = '\0'; // Null-terminate the encrypted string

    printf("\n\n\tAFTER DECRYPTION: ");

    for (i = 0; i < length; i++) {
        plain[i] = cipher[i] - key;

        // Adjust for uppercase letters
        if (isupper(cipher[i]) && plain[i] < 'A') {
            plain[i] += 26;
        }
        // Adjust for lowercase letters
        if (islower(cipher[i]) && plain[i] < 'a') {
            plain[i] += 26;
        }

        printf("%c", plain[i]);
    }
    plain[length] = '\0'; // Null-terminate the decrypted string

    printf("\n");

    return 0; // Use return 0 instead of getch();
}
```
OUTPUT :-

![Screenshot 2025-03-21 143218](https://github.com/user-attachments/assets/08ffb9c6-3e94-4a51-b782-a7fa5a05bb75)

RESULT:-

 A program has been Implemented and  the simple substitution technique named Caesar cipher using C language.

