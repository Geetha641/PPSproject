# PPSproject
#include <stdio.h>

#include <stdlib.h>

#include <string.h>

void addPlayerDetails(char *game) {

}

FILE *file;

char fileName[50];

sprintf(fileName, "%s.txt", game);

file = fopen(fileName, "a");

if (file == NULL) {

} char name[50], flatNo [10], mobileNo[15];

printf("Error opening file!\n");

exit(1);

int age;

printf("Enter player's details for %s:\n", game);

printf("Name: ");

scanf("%s", name);

printf("Age: ");

scanf("%d", &age);

printf("Flat No: ");

scanf("%s", flatNo);

printf("Mobile No: ");

scanf("%s", mobileNo);

fprintf(file, "%s %d %s %s\n", name, age, flatNo, mobileNo);

fclose(file);

printf("Player details added successfully!\n");

void displayEntries(char *game) {

FILE *file;

char fileName[50];

char line[100];

sprintf(fileName, "%s.txt", game);

file = fopen(fileName, "r");

if (file == NULL) {

}

printf("Error opening file or no entries available!\n");

exit(1);

printf("Entries for %s:\n", game);

while (fgets(line, sizeof(line), file) != NULL) {

printf("%s", line);

}

fclose(file);

} int main() {

int choice;

do {

printf("1. Player\n");

printf("2. Organizer\n");

printf("3. Exit\n");

printf("Select your option: ");

scanf("%d", &choice);

switch (choice) {

case 1:

{

char game[20];
printf("Select your game:\n");

printf("1. Chess\n");

printf("2. Carom\n");

printf("3. Badminton\n");

printf("4. Tennis\n");

printf("Enter your choice: ");

scanf("%d", &choice);

switch (choice) {

case 1:

strcpy(game, "Chess"); break;

case 2:

strcpy(game, "Carom"); break;

case 3:

strcpy(game, "Badminton"); break;

case 4:

strcpy(game, "Tennis"); break;

default:

printf("Invalid choice!\n");

}

addPlayerDetails(game); break;

}

case 2:

printf("Exiting program.\n");

break;

default:

printf("Invalid choice! Please enter a valid option.\n");

}

} while (choice != 3);

}

return 0;
