# Wanesa
// Simple guessing game
// @Unknown

#include <iostream>
#include <time.h> // Do losowania liczb, pobiera czas z komputera, żeby sekwencje się nie powtarzały
 
using namespace std;
 
int main()
{
    cout << "This is a very simple number guessing game. Each time you will be given a number of the range 0-10." << endl;
    cout << "The objective of the game is to guess whether the next number is going to be higher or not. As simple as that." << endl;
    cout << "You have the ability to make no more than 3 mistakes before you lose, so guess wisely." << endl << endl;
    cout << "You are starting with number 5. Is the next number higher(write H) or lower(write L) ?" << endl;
 
    int mistakes = 0;
    int correctGuesses;
    int prevNum = 5, nextNum;
    char choice;
 
    do
    {
        srand ( time(NULL) ); // Z czasu wyciągamy ziarno do generatora
        do
            nextNum = rand() % 11;
        while (nextNum == prevNum); // Wylosowany numer nie może być taki sam jak poprzedni
 
        cin >> choice;
 
 /*sprawdzac czy uzytk wpisal litere h */
 
        if (choice == 'H') or (choice == 'h')
        {
            if (prevNum < nextNum)
            {
                cout << "Correct ! The new number is " << nextNum << endl;
                correctGuesses++;
            }
            else if (prevNum > nextNum)
            {
                cout << "Wrong, you made a mistake ! The new number is " << nextNum << endl;
                mistakes++;
            }
        }
 
        if (choice == 'L') or (choice == 'l')
        {
            if (prevNum > nextNum)
            {
                cout << "Correct ! The new number is " << nextNum << endl;
                correctGuesses++;
            }
            else if (prevNum < nextNum)
            {
                cout << "Wrong, you made a mistake ! The new number is " << nextNum << endl;
                mistakes++;
            }
        }
 
        prevNum = nextNum;
    }
    while (mistakes < 3);
 
    cout << "You've made 3 mistakes ! Game is now over !" << endl;
    cout << "You had " << correctGuesses << " correct guesses before the game was over." << endl;
    
    while (correctGuesses > 5)
    
    cout << "Great score! Would you like to play again?";
    
    while(correctGuesses < 5)
    
    cout << "Not bad score but you could do it better!";
    cout << "Would you like to play again?";
    
 /* petla do/while */ // poziomy trudnosci
 //tryb wielosobowy
 
    return 0;
}
