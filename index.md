---
layout: base
title: Welcome To My Page 
description: Home Page
hide: true
---

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


<ul>
  <li><a class="active" href="https://darsh220.github.io/darsh_2025/">Home</a></li>
  <li><a href="https://darsh220.github.io/darsh_2025/about/">About</a></li>
  <li><a href="https://darsh220.github.io/darsh_2025/2024/09/11/PlayingwithJupyterNotebooks_IPYNB_2_.html">Hacks</a></li>
  <li><a href="https://darsh220.github.io/darsh_2025/2024/09/11/GitHub_Playground_IPYNB_2_.html">Cool thing</a></li>
</ul>



 This is a simple fun game where you can guess the number
 <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guess the Number Game</title>
    <link rel="stylesheet" href="styles.css"> <!-- Link to your CSS file -->

 <div class="game-container">
        <h1>Guess the Number Game</h1>
        <p>Guess a number between 1 and 100:</p>
        <input type="number" id="guessInput" min="1" max="100">
        <button id="guessButton" class="button">Submit Guess</button>
        <p id="feedback"></p>
        <button id="restartButton" class="button" style="display:none;">Play Again</button>
    </div>
    <script src="script.js"></script> <!-- Link to your JavaScript file -->




