#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <windows.h>
#include <ctype.h>

enum comp_moves{
    rock = 1, paper = 2, scissors = 3
};

void main()
{
    char user, play_again = 'Y';
    int computer, wins=0, losses=0, draws=0;

    while (toupper(play_again)=='Y')
    {
        //to generate a random number from computer
        srand(time(NULL));
        computer = rand() % 3 + 1;

        system("cls");

        printf(" -----|ROCK PAPER SCISSORS|-----\n\n");
        printf("options: R\tP\tS\n\n");
        printf("enter your choice: ");
        scanf(" %c", &user);

        user = toupper(user);

        printf("Computer chose: ");
        switch (computer)
        {
        case rock: printf("ROCK\n"); break;
        case paper: printf("PAPER\n"); break;
        case scissors: printf("SCISSORS\n"); break;
        }

        switch (user)
        {
        case 'R':
            if (computer == rock){
                printf("its a draw\n");
                draws++;
                Beep(800, 300);
            } else if (computer==paper){
                printf("you lose :( \n");
                losses++;
                Beep(400, 500); 
            } else {
                printf("YOU WIN\n");
                wins++;
                Beep(1000, 300); 
            }break;

        case 'P':
            if (computer == paper){
                printf("its a draw\n");
                draws++;
                Beep(800, 300);
            } else if (computer==scissors){
                printf("you lose :( \n");
                losses++;
                Beep(400, 500); 
            } else {
                printf("YOU WIN\n");
                wins++;
                Beep(1000, 300); 
            } break;

        case 'S':
            if (computer == scissors){
                printf("its a draw\n");
                draws++;
                Beep(800, 300);
            } else if (computer==rock){
                printf("you lose :( \n");
                losses++;
                Beep(400, 500); 
            } else{
                printf("YOU WIN\n");
                wins++;
                Beep(1000, 300); 
            } break;
    
    default:
        printf("*****invalid input*****\npls enter R, P or S:\n");
        break;
    }

    printf("\n-------------------SCOREBOARD-------------------\n");
    printf(" wins:      %d\n", wins);
    printf(" losses:    %d\n", losses);
    printf(" draws:     %d\n", draws);
    
    printf("\n do u want to play again? (Y/N): \n");
    scanf(" %c", &play_again);
    }

    //exit screen
    printf("\nThank you for playing Rock Paper Scissors!\n");
    printf("Final Score - Wins: %d | Losses: %d | Draws: %d\n", wins, losses, draws);
printf("\nMade by ~aadya\n        ~aashiga\n        ~munim\n        ~adhi\n        ~aashrith \n\n");
    
    Beep(800,100);
    Beep(400,100);
    Beep(500,100);
    Beep(400,100);
    Beep(500,100);
    Beep(400,100);
    Beep(500,100);
    Beep(600,100);
    Beep(600,100);
}