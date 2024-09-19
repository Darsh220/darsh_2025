---
layout: base
title: Welcome To My Page 
description: Home Page
hide: true
---
# Welcome to My Homepage!

## Explore My Work and Projects

[Get Started](#)

---

### Navigation

<ul style="list-style-type: none; padding: 0; display: flex; flex-direction: column; width: 200px;">
    <li style="margin-bottom: 10px;">
        <a href="#" style="text-decoration: none; color: #003366;">Home</a>
    </li>
    <li style="margin-bottom: 10px;">
        <a href="#" style="text-decoration: none; color: #003366;">About</a>
        <ul style="list-style-type: none; padding-left: 20px; display: none;">
            <li><a href="#" style="text-decoration: none; color: #555;">Our Team</a></li>
            <li><a href="#" style="text-decoration: none; color: #555;">Our History</a></li>
        </ul>
    </li>
    <li style="margin-bottom: 10px;">
        <a href="#" style="text-decoration: none; color: #003366;">Services</a>
        <ul style="list-style-type: none; padding-left: 20px; display: none;">
            <li><a href="#" style="text-decoration: none; color: #555;">Web Development</a></li>
            <li><a href="#" style="text-decoration: none; color: #555;">Graphic Design</a></li>
        </ul>
    </li>
    <li style="margin-bottom: 10px;">
        <a href="#" style="text-decoration: none; color: #003366;">Contact</a>
    </li>
</ul>

<script>
    // Simple JavaScript to toggle the submenu
    document.querySelectorAll('li').forEach(item => {
        item.addEventListener('click', event => {
            const submenu = item.querySelector('ul');
            if (submenu) {
                submenu.style.display = submenu.style.display === 'none' || submenu.style.display === '' ? 'block' : 'none';
            }
        });
    });
</script>

---



<div style="background-image: url('https://unblast.com/wp-content/uploads/2021/01/Space-Background-Image-2.jpg'); background-size: cover; color: white; text-align: center; padding: 50px;">
  <h1>Welcome to My Homepage!</h1>
  <p>Explore my work and projects.</p>
  <a href="https://darsh220.github.io/darsh_2025/about/" style="background-color: #808080; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px; transition: background-color 0.3s;">About</a>
</div>


<img src="https://media.tenor.com/WuNndB5UddwAAAAM/mario-monday.gif" alt="MARIO GIF">
---

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












