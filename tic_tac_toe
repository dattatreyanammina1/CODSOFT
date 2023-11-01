#include <bits/stdc++.h>
using namespace std;

// Function to display the Tic-Tac-Toe board
void displayscores(char board[3][3]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cout << board[i][j];
            if (j < 2) cout << " | ";
        }
        cout << endl;
        if (i < 2) cout << "---------" << endl;
    }
}

// Function to check if a player has won
bool checkWin(char board[3][3], char player) {
    // Check rows
    for (int i = 0; i < 3; i++) {
        if (board[i][0] == player && board[i][1] == player && board[i][2] == player)
            return true;
    }
    
    // Check columns
    for (int i = 0; i < 3; i++) {
        if (board[0][i] == player && board[1][i] == player && board[2][i] == player)
            return true;
    }
    
    // Check diagonals
    if (board[0][0] == player && board[1][1] == player && board[2][2] == player)
        return true;
    if (board[0][2] == player && board[1][1] == player && board[2][0] == player)
        return true;
    
    return false;
}

// Function to check if the game is a draw
bool checkDraw(char board[3][3]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (board[i][j] != 'X' && board[i][j] != 'O')
                return false;
        }
    }
    return true;
}

int main() {
    char board[3][3] = { { '1', '2', '3' },
                        { '4', '5', '6' },
                        { '7', '8', '9' } };
    int currentPlayer = 1; // Player 1: X, Player 2: O
    int choice;
    
    bool gameover = false;
    
    while (!gameover) {
        // Display the board
        cout << "Tic-Tac-Toe Game" << endl;
        displayscores(board);
        
        // Determine the current player
        char player = (currentPlayer == 1) ? 'X' : 'O';
        cout << "Player " << player << ", enter your choice (1-9): ";
        cin >> choice;
        
        // Input validation
        if (choice < 1 || choice > 9) {
            cout << "Invalid choice. Please choose a number from 1 to 9." << endl;
            continue;
        }
        
        // Check if the chosen cell is empty
        int row = (choice - 1) / 3;
        int col = (choice - 1) % 3;
        if (board[row][col] == 'X' || board[row][col] == 'O') {
            cout << "Cell already occupied. Choose an empty cell." << endl;
            continue;
        }
        
        // Update the board
        board[row][col] = player;
        
        // Check for a win
        if (checkWin(board, player)) {
            displayscores(board);
            cout << "Player " << player << " wins!" << endl;
            gameover = true;
        }
        
        // Check for a draw
        if (checkDraw(board)) {
            displayscores(board);
            cout << "It's a draw!" << endl;
            gameover = true;
        }
        
        // Switch players
        currentPlayer = (currentPlayer == 1) ? 2 : 1;
    }
    
    // Ask if the players want to play again
    char playAgain;
    cout << "Play again? (Y/N): ";
    cin >> playAgain;
    if (playAgain == 'Y' || playAgain == 'y') {
        // Reset the board and variables
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                board[i][j] = '1' + i * 3 + j;
            }
        }
        currentPlayer = 1;
        gameover = false;
    }
    
    return 0;
}
