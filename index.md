---
layout: base
title: Welcome To My Page 
description: Home Page
hide: true
---

<div style="background-image: url('https://media.istockphoto.com/id/1342851017/vector/elegant-black-background-vector-illustration-with-vintage-distressed-grunge-texture-and-dark.jpg?s=612x612&w=0&k=20&c=THEu64UKfhNsnXuVWOHsQehRr7uuKWjbYrshHoTFsS0='); background-size: cover; color: white; text-align: center; padding: 50px;">
  <h1>Welcome to My Homepage!</h1>
  <p>Explore my work and projects.</p>
  <a href="https://darsh220.github.io/darsh_2025/about/" style="background-color: #808080; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px; transition: background-color 0.3s;">About</a>
</div>
---

### Navigation

<style>
  .submenu {
    display: flex;
    justify-content: center;
    background: linear-gradient(90deg, #6e6e6e, #4a4a4a);
    border-radius: 8px;
    padding: 12px;
    margin: 20px 0;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
  }

  .submenu a {
    color: white;
    padding: 14px 20px;
    margin: 0 10px;
    text-decoration: none;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 16px;
    transition: background-color 0.3s, transform 0.3s;
    border-radius: 5px;
  }

  .submenu a:hover {
    background-color: rgba(255, 255, 255, 0.2);
    transform: scale(1.1);
  }
</style>

<div class="submenu">
  <a href="https://darsh220.github.io/darsh_2025/about/">About</a>
  <a href="https://darsh220.github.io/darsh_2025/2024/09/11/PlayingwithJupyterNotebooks_IPYNB_2_.html">Hacks</a>
  <a href="https://darsh220.github.io/darsh_2025/snake/">Snake Game👌</a>
  <a href="https://darsh220.github.io/darsh_2025/planning">Planning</a>
  <a href="https://darsh220.github.io/darsh_2025/cookieclicker">Cookie Clicker</a>
</div>



---





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




