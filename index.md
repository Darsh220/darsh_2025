---
layout: base
title: Welcome To My Page 
description: Home Page
hide: true
---

<div style="background-image: url('https://media.istockphoto.com/id/1342851017/vector/elegant-black-background-vector-illustration-with-vintage-distressed-grunge-texture-and-dark.jpg?s=612x612&w=0&k=20&c=THEu64UKfhNsnXuVWOHsQehRr7uuKWjbYrshHoTFsS0='); background-size: cover; color: white; text-align: center; padding: 30px; max-width: 600px; margin: 0 auto;">
  <h1>Welcome to My Homepage!</h1>
  <p>Explore my work and projects.</p>
</div>



<div class="submenu" style="max-width: 80%; margin: 0 auto; padding: 20px; text-align: center;">
  <div style="display: flex; flex-wrap: wrap; justify-content: center;">
    <div style="margin: 10px;">
      <a href="http://127.0.0.1:4100/darsh_2025/about/" style="background-color: #777; color: white; padding: 12px 24px; text-decoration: none; border-radius: 20px; font-size: 18px; display: inline-block; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); transition: transform 0.3s, box-shadow 0.3s;">About</a>
    </div>
    <div style="margin: 10px;">
      <a href="http://127.0.0.1:4100/darsh_2025/2024/09/11/GitHub_Playground_IPYNB_2_.html" style="background-color: #777; color: white; padding: 12px 24px; text-decoration: none; border-radius: 20px; font-size: 18px; display: inline-block; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); transition: transform 0.3s, box-shadow 0.3s;">Github playground</a>
    </div>
    <div style="margin: 10px;">
      <a href="http://127.0.0.1:4100/darsh_2025/2024/09/19/Hacks_Frontend_IPYNB_2_.html" style="background-color: #777; color: white; padding: 12px 24px; text-decoration: none; border-radius: 20px; font-size: 18px; display: inline-block; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); transition: transform 0.3s, box-shadow 0.3s;">Frontend</a>
    </div>
    <div style="margin: 10px;">
      <a href="http://127.0.0.1:4100/darsh_2025/snake/" style="background-color: #777; color: white; padding: 12px 24px; text-decoration: none; border-radius: 20px; font-size: 18px; display: inline-block; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); transition: transform 0.3s, box-shadow 0.3s;">Snake</a>
    </div>
  </div>
</div>

<style>
  .submenu {
    max-width: 1024px; /* Adjust width here to your desired value */
    margin: 0 auto;
    padding: 20px;
    text-align: center;
  }

  div a:hover {
    transform: translateY(-5px); /* Slight movement up */
    box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3); /* Stronger shadow on hover */
  }
</style>

<div style="text-align: center; margin: 20px;">
  <div style="display: flex; flex-wrap: wrap; justify-content: center;">
    <div style="margin: 10px;">
      <a href="http://127.0.0.1:4100/darsh_2025/cookieclicker/" style="background-color: #777; color: white; padding: 12px 24px; text-decoration: none; border-radius: 20px; font-size: 18px; display: inline-block; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); transition: transform 0.3s, box-shadow 0.3s;">Cookie Clicker</a>
    </div>
    <div style="margin: 10px;">
      <a href="http://127.0.0.1:4100/darsh_2025/2024/09/23/Sprint2selfteaching_IPYNB_2_.html" style="background-color: #777; color: white; padding: 12px 24px; text-decoration: none; border-radius: 20px; font-size: 18px; display: inline-block; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); transition: transform 0.3s, box-shadow 0.3s;">Team Teach Lesson</a>
    </div>
    <div style="margin: 10px;">
      <a href="http://127.0.0.1:4100/darsh_2025/planning/" style="background-color: #777; color: white; padding: 12px 24px; text-decoration: none; border-radius: 20px; font-size: 18px; display: inline-block; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); transition: transform 0.3s, box-shadow 0.3s;">Planning Document</a>
    </div>
    <div style="margin: 10px;">
      <a href="https://your-github-pages-link.com/random4" style="background-color: #777; color: white; padding: 12px 24px; text-decoration: none; border-radius: 20px; font-size: 18px; display: inline-block; box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2); transition: transform 0.3s, box-shadow 0.3s;">Blog Sprint 2</a>
    </div>
  </div>
  </div>

<style>
  div a:hover {
    transform: translateY(-5px); /* Slight movement up */
    box-shadow: 0 6px 15px rgba(0, 0, 0, 0.3); /* Stronger shadow on hover */
  }
</style>




---

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




