# Password-generation-
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void generatePassword(int length) {
    char characters[] = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
                        "abcdefghijklmnopqrstuvwxyz"
                        "0123456789"
                        "!@#$%^&*()_+";

    int n = sizeof(characters) - 1;
    char password[length + 1];

    for (int i = 0; i < length; i++) {
        password[i] = characters[rand() % n];
    }

    password[length] = '\0';

    printf("Generated Password: %s\n", password);
}

int main() {
    int length;

    printf("Enter password length: ");
    scanf("%d", &length);

    srand(time(NULL));  // seed value for randomness

    generatePassword(length);

    return 0;
}