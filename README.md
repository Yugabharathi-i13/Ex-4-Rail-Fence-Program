# Ex-4 Rail-Fence-Program

## NAME : YUGABHARATHI T
## REG.NO : 212224040375

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```
#include <stdio.h>
#include <string.h>
int main() {
    char text[100], rail[10][100];
    int i, j, len, rails;
    int row = 0, dir = 1;
    printf("Enter the plain text: ");
    scanf("%s", text);
    printf("Enter number of rails: ");
    scanf("%d", &rails);
    len = strlen(text);
    for (i = 0; i < rails; i++)
        for (j = 0; j < len; j++)
            rail[i][j] = ' ';
    for (i = 0; i < len; i++) {
        rail[row][i] = text[i];
        if (row == 0)
            dir = 1;
        else if (row == rails - 1)
            dir = -1;
        row += dir;
    }
    printf("Cipher text/Encrypted text: ");
    for (i = 0; i < rails; i++) {
        for (j = 0; j < len; j++) {
            if (rail[i][j] != ' ')
                printf("%c", rail[i][j]);
        }
    }
}

```

# OUTPUT
<img width="1471" height="928" alt="image" src="https://github.com/user-attachments/assets/76958d9c-15f0-412a-b9fe-ab8e6f012f7f" />


# RESULT
The Rail Fence Transposition Cipher was successfully implemented using C and the ciphertext was generated correctly for the given plaintext and number of rails.
