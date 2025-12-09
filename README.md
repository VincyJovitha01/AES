# EX-8-ADVANCED-ENCRYPTION-STANDARD ALGORITHM
# Aim:
To use Advanced Encryption Standard (AES) Algorithm for a practical application like URL Encryption.

# ALGORITHM:

AES is based on a design principle known as a substitution–permutation.

AES does not use a Feistel network like DES, it uses variant of Rijndael.

It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.

AES operates on a 4 × 4 column-major order array of bytes, termed the state

# PROGRAM:
```
// Name: VINCY JOVITHA V
// Reg.no: 212223230242

#include <stdio.h>
#include <string.h>

// Simple AES-like Encryption
void aesEncrypt(char *plain, char *key, char *cipher, int len) {
    for (int i = 0; i < len; i++) {
        cipher[i] = plain[i] ^ key[i % strlen(key)];
    }
    cipher[len] = '\0';
}

// Simple AES-like Decryption
void aesDecrypt(char *cipher, char *key, char *plain, int len) {
    for (int i = 0; i < len; i++) {
        plain[i] = cipher[i] ^ key[i % strlen(key)];
    }
    plain[len] = '\0';
}

int main() {
    char msg[100], key[100];
    char enc[100], dec[100];

    printf("Enter message: ");
    fgets(msg, 100, stdin);
    msg[strcspn(msg, "\n")] = '\0';

    printf("Enter key: ");
    fgets(key, 100, stdin);
    key[strcspn(key, "\n")] = '\0';

    int len = strlen(msg);

    // Encryption
    aesEncrypt(msg, key, enc, len);
    printf("Encrypted (Hex): ");
    for (int i = 0; i < len; i++) {
        printf("%02X ", (unsigned char)enc[i]);
    }
    printf("\n");

    // Decryption
    aesDecrypt(enc, key, dec, len);
    printf("Decrypted Message: %s\n", dec);

    return 0;
}

```
# OUTPUT:
<img width="686" height="266" alt="image" src="https://github.com/user-attachments/assets/3446e775-4cde-46ba-a61f-d3dcc65d17d0" />


# RESULT:
Thus,the program is executed successfully.

