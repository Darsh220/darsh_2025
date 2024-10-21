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


<div class="submenu">
  <div class="card-container">
    <a href="https://darsh220.github.io/darsh_2025/about/">About</a>
    <a href="https://darsh220.github.io/darsh_2025/2024/09/11/GitHub_Playground_IPYNB_2_.html">GitHub Playground</a>
    <a href="https://darsh220.github.io/darsh_2025/2024/09/19/Hacks_Frontend_IPYNB_2_.html">Frontend</a>
    <a href="https://darsh220.github.io/darsh_2025/snake/">Snake</a>
    <a href="https://darsh220.github.io/darsh_2025/cookieclicker/">Cookie Clicker</a>
    <a href="https://darsh220.github.io/darsh_2025/2024/09/25/big-idea-3-10-3_IPYNB_2_.html">Team Teach Lesson</a>
    <a href="https://darsh220.github.io/darsh_2025/summary/">Summary</a>
    <a href="https://darsh220.github.io/darsh_2025/2024/10/15/sprint2_blog_IPYNB_2_.html">Blog Sprint 2</a>
  </div>
</div>

<style>
  .submenu {
    max-width: 1024px;
    margin: 20px auto;
    padding: 20px;
    text-align: center;
    background-color: #000000;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  }

  .card-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
  }

  .card-container a {
    background-color: #333333;
    color: white;
    padding: 12px 18px;
    text-decoration: none;
    border-radius: 5px;
    font-size: 16px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    transition: transform 0.2s, box-shadow 0.2s, background-color 0.2s;
    display: block;
    text-align: center;
  }

  .card-container a:hover {
    transform: translateY(-3px);
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.3);
    background-color: #444444;
  }
</style>


---


<table>
  <tr>
    <th>Lesson</th>
    <th>Link</th>
  </tr>
  <tr>
    <td>3.1</td>
    <td><a href="https://darsh220.github.io/darsh_2025/2024/10/07/3.1_IPYNB_2_.html" title="Learn about Lesson 3.1">Lesson 3.1</a></td>
  </tr>
  <tr>
    <td>3.2</td>
    <td><a href="https://darsh220.github.io/darsh_2025/2024/10/07/3.2_IPYNB_2_.html" title="Learn about Lesson 3.2">Lesson 3.2</a></td>
  </tr>
  <tr>
    <td>3.3</td>
    <td><a href="https://darsh220.github.io/darsh_2025/2024/10/09/3.3_3.5_IPYNB_2_.html" title="Learn about Lesson 3.3">Lesson 3.3</a></td>
  </tr>
  <tr>
    <td>3.4</td>
    <td><a href="https://darsh220.github.io/darsh_2025/2024/10/11/3.4_IPYNB_2_.html" title="Learn about Lesson 3.4">Lesson 3.4</a></td>
  </tr>
  <tr>
    <td>3.5</td>
    <td><a href="https://darsh220.github.io/darsh_2025/2024/10/09/3.3_3.5_IPYNB_2_.html" title="Learn about Lesson 3.5">Lesson 3.5</a></td>
  </tr>
  <tr>
    <td>3.6</td>
    <td><a href="https://darsh220.github.io/darsh_2025/2024/10/10/3.6_IPYNB_2_.html" title="Learn about Lesson 3.6">Lesson 3.6</a></td>
  </tr>
  <tr>
    <td>3.7</td>
    <td><a href="https://darsh220.github.io/darsh_2025/2024/10/11/3.7_IPYNB_2_.html" title="Learn about Lesson 3.7">Lesson 3.7</a></td>
  </tr>
  <tr>
    <td>3.8</td>
    <td><a href="https://darsh220.github.io/darsh_2025/2024/10/03/3.8_IPYNB_2_.html" title="Learn about Lesson 3.8">Lesson 3.8</a></td>
  </tr>
</table>


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






