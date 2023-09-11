#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main()

{
        
        // constants
        const int min_card = 1;
        const int max_card = 10;

        int card1;
        int card2;
        int total;
        int nextCard;
        char hitStay;
        char newGame;
        int hand;
        int game;
        int nextTotal;  
        unsigned seed = time(0);
        bool playAgain = true;
        while (playAgain) {
            
        srand(seed);

        cout << "Welcome to Cat's Casino! Dealing your first cards...\n";
        card1 = (rand() % (max_card - min_card + 1)) + min_card;
        card2= (rand() % (max_card - min_card + 1)) + min_card;
        cout << card1 << " " << card2 << endl;
        total = (card1 + card2);
        cout << "Total: " << total << endl;

        while (total <= 21)
        {
                cout << "Do you want another card? ";
                cin >> hitStay;
            if (hitStay == 'n') {
                cout << "Thank you for playing!";
            }
            
        if (hitStay == 'y') {
                cout << "Dealing next card...\n";
                nextCard = (rand() % (max_card - min_card + 1)) + min_card;
                cout << nextCard << endl;
                total = total + nextCard;
                cout << "Total: " << total << endl;
            }
            if (total > 21) {
                cout << "You lose!\n";
                cout << "Would you like to play again? ";
                cin >> newGame;
            if (newGame == 'n') {
                playAgain = false;
                cout << "Thank you for playing!";
            }
            }
            else if (hitStay == 'n') {
                cout << "Would you like to play again? ";
                cin >> newGame;
            }
            if (newGame == 'n') {
                playAgain = false;
                cout << "Thank you for playing!";
            }
        
        }
    }
        
} 
