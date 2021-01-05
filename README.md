INTRODUCTION TO TIC TAC TOE GAME
Tic-tac-toe is a pencil and-paper game for two players, X and O, who take turns marking the spaces in a 3×3 grid. The player who succeeds in placing three respective marks in a horizontal, vertical, or diagonal row wins the game. Introduction to Tic Tac Toe (Console Game) C++ Program.
 This program is a game program, Tic Tac Toe. Most of us have played this game in school days, we have make a C++ program on it.

INTRODUCTION OF THE GAME AS A PROGRAM
This game uses board to control players, in each turn players enter a number and choose a move Simplify programing assumes that player one always moves first and uses X Player two moves at 2nd position and uses O.







STRUCTURE OF PROGRAM
At the time when program start we initialize variables, and we run the game loop until the game end or players choose to quit. The game consists of three steps: 
• Display board
 • Get players move 
• Check for game end
INITIALIZATION OF VARIABLES
 
This portion of code is for initialization of variables, the variables of squares are initializing with the characters from 1 to 9.
 The player turn will be initializing to 1 because since the player 1 makes the first turn. Game over is initialize to true but that does not really matter for this program because after game loop game check itself for winner.

GAME LOOP
After initialization game began to move forward for main game loop these loops are while and do while loop which are encapsulated in statements that what to do or not to do. 
Once we enter the game loop The first thing will be done is print the game board which displays the tic tac toe game board in console window Remember we initialize these squares with characters from 1 to 9 for basic console input and output.

GAME LOOPS (PLAYERS SIGN INITIALIZATION)
Mark determines that first player has X and second has 0 This portion of statements check for player turn if it's not the first player move its promoted the move to next player Then the next line gets the valid move of the player. 
GAME LOOPS (INVALID MOVE)
If players input an invalid move it's prompted for another move and says try again like this...
 

GAME LOOPS (VALID MOVE)
The cin statement gets the valid move for the player Notice that it's begin with another loop it has pretty much statements to check the conditions. The check for valid move is pretty large branch of square check.
 
GAME LOOPS (PLAYERS MOVE) 
Each branch of the if statement makes two check, the first input check that the input is valid digit from 1 to 9 and second check is for make sure of the input is digit not an character, second check also make sure that the number which is entered not entered previously.
 

GAME LOOPS (CONDITION CHECK FOR WINNER)
After the valid move the series of checks perform to check the games conditions. Note there are the nine ways to end the game, 8 conditions to win the game and 1 condition for draw the game. 

i)	The first conditions check the ending game condition through the walls of 1st square.
  




ii)	The second if statement handles the 4 cases from the middle 5th square.
  

iii)	The third if statement handles the 2 cases from the 9th square
  

GAME LOOPS (MATCH DRAW)
In each of these cases we check that the squares not equals to its number character. This check ensures that we have an extra O and the other two checks make sure that the other two squares have the same O in the series like this one Those cases cover the win condition however game will be ended and draw like this.
 
GAME LOOPS (FINAL CHECK)
The final check takes cover of the case that game will be draw and all the squares will be marked.
 When we determine that the game is over we run through over final condition.
 If the game is over we check for the game that someone is win the game Boolean which we set at the last part, if some has won then it will be last one or last player which is moved.
 

OUTPUT OF PROGRAM









SOURCE CODE
#include <iostream.h>
#include <conio.h>
char square[10] = {'o','1','2','3','4','5','6','7','8','9'};
int checkwin();
void board();
void main()
{
	int player = 1,i,choice;
	char mark;
	clrscr();
	do
	{
		board();
		player=(player%2)?1:2;
		cout << "Player " << player << ", enter a number:  ";
		cin >> choice;
		mark=(player == 1) ? 'X' : 'O';
		if (choice == 1 && square[1] == '1')
			square[1] = mark;
		else if (choice == 2 && square[2] == '2')
			square[2] = mark;
		else if (choice == 3 && square[3] == '3')
			square[3] = mark;
		else if (choice == 4 && square[4] == '4')
			square[4] = mark;
		else if (choice == 5 && square[5] == '5')
			square[5] = mark;
		else if (choice == 6 && square[6] == '6')
			square[6] = mark;
		else if (choice == 7 && square[7] == '7')
			square[7] = mark;
		else if (choice == 8 && square[8] == '8')
			square[8] = mark;
		else if (choice == 9 && square[9] == '9')
			square[9] = mark;
		else
		{
			cout<<"Invalid move ";
			player--;
			getch();
		}
		i=checkwin();
		player++;
	}while(i==-1);
	board();
	if(i==1)
		cout<<"==>\aPlayer "<<--player<<" win ";
	else
		cout<<"==>\aGame draw";
	getch();
}




int checkwin()
{
	if (square[1] == square[2] && square[2] == square[3])
		return 1;
	else if (square[4] == square[5] && square[5] == square[6])
		return 1;
	else if (square[7] == square[8] && square[8] == square[9])
		return 1;
	else if (square[1] == square[4] && square[4] == square[7])
		return 1;
	else if (square[2] == square[5] && square[5] == square[8])
		return 1;
	else if (square[3] == square[6] && square[6] == square[9])
		return 1;
	else if (square[1] == square[5] && square[5] == square[9])
		return 1;
	else if (square[3] == square[5] && square[5] == square[7])
		return 1;
	else if (square[1] != '1' && square[2] != '2' && square[3] != '3' &&
		 square[4] != '4' && square[5] != '5' && square[6] != '6' &&
	    square[7] != '7' && square[8] != '8' && square[9] != '9')
		return 0;
	else
		return -1;
}



void board()
{
	clrscr();
	cout << "\n\n\tTic Tac Toe\n\n";
	cout<<"\tMADE BY ARJUN"<<"\n";
	cout<<"\n";
	cout << "Player 1 (X)  -  Player 2 (O)" << endl << endl;
	cout << endl;
	cout << "     |     |     " << endl;
	cout << "  " << square[1] << "  |  " << square[2] << "  |  " << square[3] << endl;
	cout << "_____|_____|_____" << endl;
	cout << "     |     |     " << endl;
	cout << "  " << square[4] << "  |  " << square[5] << "  |  " << square[6] << endl;
	cout << "_____|_____|_____" << endl;
	cout << "     |     |     " << endl;
	cout << "  " << square[7] << "  |  " << square[8] << "  |  " << square[9] << endl;
	cout << "     |     |     " << endl << endl;
}
