 Rail Fence Cipher
 Rail Fence Cipher using with different key values
 AIM:
 To develop a simple C program to implement Rail Fence Cipher.
 DESIGN STEPS:
 Step 1:
 Design of Rail Fence Cipher algorithnm
 Step 2:
 Implementation using C or pyhton code
 Step 3:
 Testing algorithm with different key values. ALGORITHM DESCRIPTION: In the rail fence cipher, the
 plaintext is written downwards and diagonally on successive "rails" of an imaginary fence, then
 moving up when we reach the bottom rail. When we reach the top rail, the message is written
 downwards again until the whole plaintext is written out. The message is then read off in rows.
 PROGRAM:
 #include <stdio.h>
 #include <string.h>
 int main() {
 int i, j, k, l;
 char a[20], c[20], d[20];
 printf("\n\t\tRAIL FENCE TECHNIQUE\n");
 // Safely getting input string using fgets instead of gets
 printf("\nEnter the input string: ");
 fgets(a, sizeof(a), stdin);
 // Removing the newline character if it exists
 a[strcspn(a, "\n")] = '\0';
 l = strlen(a); // Get the length of the input string
 // Rail fence encryption: first collect even indices, then odd
 for (i = 0, j = 0; i < l; i++) {
 if (i % 2 == 0) {
 c[j++] = a[i];
 }
 }
 for (i = 0; i < l; i++) {
 if (i % 2 == 1) {
 c[j++] = a[i];
 }
 }
 c[j] = '\0'; // Null-terminate the encrypted string
 printf("\nCipher text after applying rail fence: %s\n", c);
 // Rail fence decryption
 if (l % 2 == 0) {
 k =l / 2;
 } else {
 k =(l / 2) + 1;
 }
 1/2
 https://github.com/23012238/Cryptography---19CS412-classical-techqniques/tree/main
19/03/2025, 21:02
 23012238/Cryptography---19CS412-classical-techqniques
 // Reconstructing the original text
 for (i = 0, j = 0; i < k; i++) {
 d[j] = c[i];
 j += 2;
 }
 for (i = k, j = 1; i < l; i++) {
 d[j] = c[i];
 j += 2;
 }
 d[l] = '\0'; // Null-terminate the decrypted string
 printf("\nText after decryption: %s\n", d);
 return 0; // Properly return from main
 }
 OUTPUT:
 RESULT:
 The program is executed successfully
