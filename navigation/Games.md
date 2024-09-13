---
layout: page
title: Games
description: Games
permalink: /Games/
---

Welcome to Tic Tac Toe!

# Tic, Tac Toe
<style>
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

#game {
    text-align: center;
    background: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

#board {
    display: grid;
    grid-template-columns: repeat(3, 100px);
    grid-template-rows: repeat(3, 100px);
    gap: 5px;
    margin-bottom: 20px;
}

.cell {
    width: 100px;
    height: 100px;
    background-color: #eee;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 2em;
    cursor: pointer;
    border: 2px solid #ddd;
    border-radius: 5px;
}

.cell:hover {
    background-color: #ddd;
}

#status {
    font-size: 1.2em;
    margin-bottom: 10px;
}

button {
    padding: 10px 20px;
    background-color: #007BFF;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}
</style>

<div id="game">
    <h1>Tic-Tac-Toe</h1>
    <div id="board">
        <div class="cell" onclick="makeMove(this)"></div>
        <div class="cell" onclick="makeMove(this)"></div>
        <div class="cell" onclick="makeMove(this)"></div>
        <div class="cell" onclick="makeMove(this)"></div>
        <div class="cell" onclick="makeMove(this)"></div>
        <div class="cell" onclick="makeMove(this)"></div>
        <div class="cell" onclick="makeMove(this)"></div>
        <div class="cell" onclick="makeMove(this)"></div>
        <div class="cell" onclick="makeMove(this)"></div>
    </div>
    <p id="status">Player X's turn</p>
    <button onclick="resetGame()">Reset Game</button>
</div>

<script>
let currentPlayer = 'X';
let board = ['', '', '', '', '', '', '', '', ''];
const status = document.getElementById('status');
const cells = document.querySelectorAll('.cell');

function makeMove(cell) {
    const index = Array.from(cells).indexOf(cell);
    
    if (board[index] === '' && !checkWinner()) {
        board[index] = currentPlayer;
        cell.textContent = currentPlayer;
        if (checkWinner()) {
            status.textContent = `Player ${currentPlayer} wins!`;
        } else if (board.every(cell => cell !== '')) {
            status.textContent = 'It\'s a draw!';
        } else {
            currentPlayer = currentPlayer === 'X' ? 'O' : 'X';
            status.textContent = `Player ${currentPlayer}'s turn`;
        }
    }
}

function checkWinner() {
    const winningCombos = [
        [0, 1, 2], [3, 4, 5], [6, 7, 8], // Rows
        [0, 3, 6], [1, 4, 7], [2, 5, 8], // Columns
        [0, 4, 8], [2, 4, 6] // Diagonals
    ];
    
    return winningCombos.some(combo => {
        const [a, b, c] = combo;
        return board[a] && board[a] === board[b] && board[a] === board[c];
    });
}

function resetGame() {
    board = ['', '', '', '', '', '', '', '', ''];
    cells.forEach(cell => cell.textContent = '');
    currentPlayer = 'X';
    status.textContent = `Player ${currentPlayer}'s turn`;
}
</script>


Welcome to Rock Paper Scissors!

# Rock, Paper, Scissors Game

<style>
body {
    font-family: Arial, sans-serif;
    background-color: #f4f4f4;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

#game {
    text-align: center;
    background: #fff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

button {
    padding: 10px 20px;
    background-color: #007BFF;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 1em;
    margin: 5px;
}

button:hover {
    background-color: #0056b3;
}

#result {
    margin-top: 20px;
    font-size: 1.2em;
}
</style>

<div id="game">
    <h1>Rock, Paper, Scissors</h1>
    <button onclick="play('rock')">Rock</button>
    <button onclick="play('paper')">Paper</button>
    <button onclick="play('scissors')">Scissors</button>
    <p id="result">Make your move!</p>
</div>

<script>
function play(playerChoice) {
    const choices = ['rock', 'paper', 'scissors'];
    const computerChoice = choices[Math.floor(Math.random() * 3)];
    const resultElement = document.getElementById('result');

    let result = '';
    if (playerChoice === computerChoice) {
        result = `It's a tie! Both chose ${playerChoice}.`;
    } else if (
        (playerChoice === 'rock' && computerChoice === 'scissors') ||
        (playerChoice === 'paper' && computerChoice === 'rock') ||
        (playerChoice === 'scissors' && computerChoice === 'paper')
    ) {
        result = `You win! ${playerChoice} beats ${computerChoice}.`;
    } else {
        result = `You lose! ${computerChoice} beats ${playerChoice}.`;
    }

    resultElement.textContent = result;
}
</script>