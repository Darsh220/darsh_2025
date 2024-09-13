---
layout: base
title: Welcome To My Page 
description: Home Page
hide: true
---
<ul>
  <li><a class="active" href="https://darsh220.github.io/darsh_2025/">Home</a></li>
  <li><a href="https://darsh220.github.io/darsh_2025/about/">About</a></li>
  <li><a href="https://darsh220.github.io/darsh_2025/2024/09/11/PlayingwithJupyterNotebooks_IPYNB_2_.html">Hacks</a></li>
   <li><a href="https://darsh220.github.io/darsh_2025/snake/">Snake Game</a></li>
   <li><a href="https://darsh220.github.io/darsh_2025/Games/">Games</a></li>

</ul>
This is my page 
<img src="https://media.tenor.com/WuNndB5UddwAAAAM/mario-monday.gif" alt="MARIO GIF">


<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #111;
}
</style>



# Guess the Number Game

<p>Guess a number between 1 and 100:</p>

<input type="number" id="guessInput" min="1" max="100">
<button id="guessButton" class="button">Submit Guess</button>
<p id="feedback"></p>
<button id="restartButton" class="button" style="display:none;">Play Again</button>

<script>
document.addEventListener('DOMContentLoaded', function() {
    const guessInput = document.getElementById('guessInput');
    const guessButton = document.getElementById('guessButton');
    const feedback = document.getElementById('feedback');
    const restartButton = document.getElementById('restartButton');

    let secretNumber;
    let attempts = 0;

    function startNewGame() {
        secretNumber = Math.floor(Math.random() * 100) + 1;
        attempts = 0;
        feedback.textContent = '';
        guessInput.value = '';
        guessInput.disabled = false;
        guessButton.disabled = false;
        restartButton.style.display = 'none';
    }

    function checkGuess() {
        const userGuess = parseInt(guessInput.value, 10);
        if (isNaN(userGuess) || userGuess < 1 || userGuess > 100) {
            feedback.textContent = 'Please enter a number between 1 and 100.';
            return;
        }

        attempts++;

        if (userGuess === secretNumber) {
            feedback.textContent = `Congratulations! You guessed the number in ${attempts} attempts.`;
            guessInput.disabled = true;
            guessButton.disabled = true;
            restartButton.style.display = 'inline-block';
        } else if (userGuess < secretNumber) {
            feedback.textContent = 'Too low! Try again.';
        } else {
            feedback.textContent = 'Too high! Try again.';
        }
    }

    guessButton.addEventListener('click', checkGuess);
    restartButton.addEventListener('click', startNewGame);

    startNewGame(); // Initialize the game
});
</script>

<style>
/* Add some basic styles */
.button {
    padding: 10px 20px;
    font-size: 16px;
    color: #fff;
    background-color: #007bff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s;
    margin: 10px;
}

.button:hover {
    background-color: #0056b3;
}
</style>


# Random Emoji Generator

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

#emoji {
    margin-top: 20px;
    font-size: 3em;
}
</style>

<div id="game">
    <h1>Random Emoji Generator</h1>
    <button onclick="generateEmoji()">Generate Emoji</button>
    <p id="emoji">😀</p>
</div>

<script>
function generateEmoji() {
    const emojis = ['😀', '😂', '😍', '🤔', '😎', '🤯', '😜', '🙃', '🥳', '🤩'];
    const randomEmoji = emojis[Math.floor(Math.random() * emojis.length)];
    const emojiElement = document.getElementById('emoji');
    emojiElement.textContent = randomEmoji;
}
</script>










