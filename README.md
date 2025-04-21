## EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER
 

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


## PROGRAM :
```
#include <stdio.h> 
#include <string.h>
#include <ctype.h> 

int main() {
    char plain[10], cipher[10]; 
    int key, i, length;

    printf("\n Enter the plain text: ");
    scanf("%s", plain);

    printf("\n Enter the key value: ");
    scanf("%d", &key);

    printf("\n \n \t PLAIN TEXT: %s", plain);
    printf("\n \n \t ENCRYPTED TEXT: ");
    
    for (i = 0, length = strlen(plain); i < length; i++) {
        cipher[i] = plain[i] + key;
        if (isupper(plain[i]) && (cipher[i] > 'Z')) 
            cipher[i] = cipher[i] - 26;
        if (islower(plain[i]) && (cipher[i] > 'z')) 
            cipher[i] = cipher[i] - 26;
        printf("%c", cipher[i]);
    }

    printf("\n \n \t AFTER DECRYPTION : ");
    for (i = 0; i < length; i++) {
        plain[i] = cipher[i] - key; 
        if (isupper(cipher[i]) && (plain[i] < 'A')) 
            plain[i] = plain[i] + 26; 
        if (islower(cipher[i]) && (plain[i] < 'a')) 
            plain[i] = plain[i] + 26; 
        printf("%c", plain[i]);
    }

    printf("\n");
    return 0;
}
```

## OUTPUT :

![Screenshot 2025-04-21 084414](https://github.com/user-attachments/assets/e5fff2e2-6f4e-43d6-ae4a-419ea50c92a8)

## RESULT :
 Thus the implementation of caser cipher is sucessfully implented.
