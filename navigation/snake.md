---
layout: page
title: snake
description: Snake Game
permalink: /snake/
---

<h1>Welcome to the Snake Game!!! (Use W/A/S/D or Arrow keys to control the snake.)</h1>
<canvas id="snakeGame" width="400" height="400"></canvas>
<button id="startButton" onclick="startGame()">Start Game</button>
<style>
    #snakeGame {
        border: 1px solid black;
        background-color: #F0F0F0;
        margin-bottom: 20px;
    }
    body {
        font-family: sans-serif;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        height: 100vh;
        background-color: #eaeaea;
    }
    h1 {
        color: #333;
    }
    #startButton {
        padding: 10px 20px;
        font-size: 16px;
        border: none;
        border-radius: 5px;
        background-color: #4CAF50;
        color: white;
        cursor: pointer;
        transition: background-color 0.3s;
    }
    #startButton:hover {
        background-color: #45a049;
    }
</style>

<script>
    const canvas = document.getElementById('snakeGame');
    const ctx = canvas.getContext('2d');
    const box = 20;
    let snake, direction, food, score, level, speed, game;

    function startGame() {
        snake = [{ x: 8 * box, y: 8 * box }];
        direction = 'RIGHT';
        food = generateFood();
        score = 0;
        level = 1;
        speed = 150;
        clearInterval(game);
        game = setInterval(draw, speed);  // Start the game
    }

    function generateFood() {
        return {
            x: Math.floor(Math.random() * 19) * box,
            y: Math.floor(Math.random() * 19) * box,
        };
    }

    // Prevent page scrolling when using arrow keys and WASD
    window.addEventListener('keydown', function(event) {
        if (['ArrowUp', 'ArrowDown', 'ArrowLeft', 'ArrowRight', 'w', 'a', 's', 'd'].includes(event.key)) {
            event.preventDefault();
        }
    });
    document.addEventListener('keydown', changeDirection);

    function changeDirection(event) {
        if ((event.key === 'ArrowUp' || event.key === 'w') && direction !== 'DOWN') direction = 'UP';
        else if ((event.key === 'ArrowDown' || event.key === 's') && direction !== 'UP') direction = 'DOWN';
        else if ((event.key === 'ArrowLeft' || event.key === 'a') && direction !== 'RIGHT') direction = 'LEFT';
        else if ((event.key === 'ArrowRight' || event.key === 'd') && direction !== 'LEFT') direction = 'RIGHT';
    }

    function drawSnake() {
        for (let i = 0; i < snake.length; i++) {
            ctx.fillStyle = i === 0 ? 'green' : 'lightgreen';
            ctx.fillRect(snake[i].x, snake[i].y, box, box);
            ctx.strokeStyle = 'darkgreen';
            ctx.strokeRect(snake[i].x, snake[i].y, box, box);
        }
    }

    function drawFood() {
        ctx.fillStyle = 'red';
        ctx.fillRect(food.x, food.y, box, box);
    }

    function updateSnake() {
        let head = { ...snake[0] };
        if (direction === 'UP') head.y -= box;
        if (direction === 'DOWN') head.y += box;
        if (direction === 'LEFT') head.x -= box;
        if (direction === 'RIGHT') head.x += box;

        // Game Over conditions
        if (head.x < 0 || head.x >= 400 || head.y < 0 || head.y >= 400 || collision(head, snake)) {
            clearInterval(game);
            alert('Game Over! Your score: ' + score);
            startGame();  // Restart the game
        }
        if (head.x === food.x && head.y === food.y) {
            score++;
            food = generateFood();
            increaseLevel();
        } else {
            snake.pop();
        }
        snake.unshift(head);
    }

    function collision(head, array) {
        for (let i = 1; i < array.length; i++) {
            if (head.x === array[i].x && head.y === array[i].y) return true;
        }
        return false;
    }

    function draw() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        drawSnake();
        drawFood();
        updateSnake();
        ctx.fillStyle = 'black';
        ctx.font = '20px Arial';
        ctx.fillText('Score: ' + score, 10, 20);
        ctx.fillText('Level: ' + level, 10, 40);
    }

    function increaseLevel() {
        if (score % 5 === 0) { // Increase level every 5 cookies
            level++;
            clearInterval(game);
            speed = Math.max(50, speed - 20); // Increase speed, up to a minimum
            game = setInterval(draw, speed);
        }
    }
</script>
