#include <iostream>
using namespace std;

// Function to print the game board
void printBoard(char board[3][3]) {
    cout << "-------------" << endl;
    for (int i = 0; i < 3; i++) {
        cout << "| ";
        for (int j = 0; j < 3; j++) {
            cout << board[i][j] << " | ";
        }
        cout << endl;
        cout << "-------------" << endl;
    }
}

// Function to check if a player has won
bool checkWin(char board[3][3], char player) {
    // Check rows, columns, and diagonals
    for (int i = 0; i < 3; i++) {
        if (board[i][0] == player && board[i][1] == player && board[i][2] == player) {
            return true; // row
        }
        if (board[0][i] == player && board[1][i] == player && board[2][i] == player) {
            return true; // column
        }
    }
    if (board[0][0] == player && board[1][1] == player && board[2][2] == player) {
        return true; // diagonal
    }
    if (board[0][2] == player && board[1][1] == player && board[2][0] == player) {
        return true; // diagonal
    }
    return false;
}

// Function to check if the board is full (draw)
bool isBoardFull(char board[3][3]) {
    // Loop through the entire board to check if any cell is empty
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (board[i][j] == ' ') {
                return false; // If an empty space is found, return false
            }
        }
    }
    return true; // If no empty space is found, return true (board is full)
}

int main() {
    char board[3][3] = { { ' ', ' ', ' ' }, { ' ', ' ', ' ' }, { ' ', ' ', ' ' } };
    int row, col;
    char currentPlayer = 'X';

    // Game loop
    while (true) {
        printBoard(board);
        cout << "Player " << currentPlayer << "'s turn." << endl;
        cout << "Enter row (0, 1, or 2): ";
        cin >> row;
        cout << "Enter column (0, 1, or 2): ";
        cin >> col;

        // Validate input
        if (row < 0 || row > 2 || col < 0 || col > 2 || board[row][col] != ' ') {
            cout << "Invalid move. Try again." << endl;
            continue;
        }

        // Place the current player's mark
        board[row][col] = currentPlayer;

        // Check for a win
        if (checkWin(board, currentPlayer)) {
            printBoard(board);
            cout << "Player " << currentPlayer << " wins!" << endl;
            break;
        }

        // Check for a draw
        if (isBoardFull(board)) {
            printBoard(board);
            cout << "It's a draw!" << endl;
            break;
        }

        // Switch to the other player
        currentPlayer = (currentPlayer == 'X') ? 'O' : 'X';
    }

    return 0;
}
