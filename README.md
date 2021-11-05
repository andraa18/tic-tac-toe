#include <iostream>
#include <conio.h>

using namespace std;

char board[3][3] = {' ',' ',' '
                    ' ',' ',' '
                    ' ',' ',' '};
int turn = 1;
char mark = 'O';
int input;

void InputMatrix()
{
	cout << " 1 | 2 | 3 " <<;
	cout << " __________" <<;
	cout << " 4 | 5 | 6 " <<;
	cout << " __________" <<;
	cout << " 7 | 8 | 9 " <<;
	cout << " __________" <<;
}

void Board()
{
	cout << " " << board[0][0] << " | " << board[0][1] << " | " board[0][2] << " " <<;
	cout << " __________" <<;
	cout << " " << board[1][0] << " | " << board[1][1] << " | " board[1][2] << " " <<;
	cout << " __________" <<;
	cout << " " << board[2][0] << " | " << board[2][1] << " | " board[2][2] << " " <<;
}

int Mark()
{
	for(int i=0, k=1; i<3; i++)
		for(int j=0; j<3; j++)
			if(board[i][i] == ' ')
				{
				board[i][j] = mark;
				return 1;
				}
			  else
				{
				cout << "invalid input";
				hetch();
				return 0;
				}
|}

int check()
{
	if(board[0][0] == mark && board[0][1] == mark && board[0][2]) return 1;
	if(board[1][0] == mark && board[1][1] == mark && board[1][2]) return 1;
	if(board[2][0] == mark && board[2][1] == mark && board[2][2]) return 1;
	
	if(board[0][0] == mark && board[1][0] == mark && board[2][0]) return 1;
	if(board[0][1] == mark && board[1][1] == mark && board[2][1]) return 1;
	if(board[0][2] == mark && board[1][2] == mark && board[2][2]) return 1;
}

int main ()
{
	int won = 0;
	int ValidInput = 0;
	
	for(int i=0; i<9; i++;)
		{
		system("cls");
		Board();
		if(turn) cout << "player 1 turn (Symbol: O)" << endl;
		  else cout << "player 2 turn (Symbol: O)" << endl;
		InputMatrix();
		cout << "enter input from Input Matrix: ";
		cin >> input;
		while(input < 0 || input > 9)
			{
			cout << "invalid input" << endl << "please enter input";
			cin >> input;
			}
		if(turn) mark = 'O';
		  else mark = 'X';
		ValidInput = Mark();
		if(!ValidInput)
			{
			i--;
			continue;
			}
		won = check();
		if(won)
			{
			system("cls");
			Board();
			if(turn) cout << endl << "player 1 won";
			  else cout << endl << "player 2 won";
			getch();
			break;
			}
		if(i==8)
			{
			system("cls");
			Board();
			cout << endl << "match draw";
			}
		turn = !turn;
		}
		  
	return 0;
}
