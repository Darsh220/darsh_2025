---
layout: base
title: Welcome To My Page 
description: Home Page
hide: true
---

This is my page 
<img src="https://media.tenor.com/WuNndB5UddwAAAAM/mario-monday.gif" alt="MARIO GIF">

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Snake Game</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
            margin: 0;
        }
        canvas {
            background-color: #000;
        }
    </style>
</head>
<body>
    <canvas id="snakeGame" width="400" height="400"></canvas>
    <script>
        const canvas = document.getElementById('snakeGame');
        const ctx = canvas.getContext('2d');

        const scale = 20;
        const rows = canvas.height / scale;
        const columns = canvas.width / scale;

        let snake = [{ x: Math.floor(columns / 2) * scale, y: Math.floor(rows / 2) * scale }];
        let food = { x: Math.floor(Math.random() * columns) * scale, y: Math.floor(Math.random() * rows) * scale };
        let direction = 'RIGHT';
        let newDirection = 'RIGHT';
        let score = 0;

        function draw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = 'green';
            snake.forEach(segment => ctx.fillRect(segment.x, segment.y, scale, scale));
            
            ctx.fillStyle = 'red';
            ctx.fillRect(food.x, food.y, scale, scale);

            ctx.fillStyle = 'white';
            ctx.font = '20px Arial';
            ctx.fillText('Score: ' + score, 10, 20);
        }

        function update() {
            let head = { ...snake[0] };
            if (direction === 'LEFT') head.x -= scale;
            if (direction === 'RIGHT') head.x += scale;
            if (direction === 'UP') head.y -= scale;
            if (direction === 'DOWN') head.y += scale;

            if (head.x === food.x && head.y === food.y) {
                score++;
                food = { x: Math.floor(Math.random() * columns) * scale, y: Math.floor(Math.random() * rows) * scale };
            } else {
                snake.pop();
            }

            snake.unshift(head);

            if (head.x < 0 || head.x >= canvas.width || head.y < 0 || head.y >= canvas.height || snake.slice(1).some(segment => segment.x === head.x && segment.y === head.y)) {
                alert('Game Over! Your score is ' + score);
                snake = [{ x: Math.floor(columns / 2) * scale, y: Math.floor(rows / 2) * scale }];
                direction = 'RIGHT';
                score = 0;
            }
        }

        function gameLoop() {
            draw();
            update();
            setTimeout(gameLoop, 100);
        }

        document.addEventListener('keydown', event => {
            if (event.key === 'ArrowUp' && direction !== 'DOWN') newDirection = 'UP';
            if (event.key === 'ArrowDown' && direction !== 'UP') newDirection = 'DOWN';
            if (event.key === 'ArrowLeft' && direction !== 'RIGHT') newDirection = 'LEFT';
            if (event.key === 'ArrowRight' && direction !== 'LEFT') newDirection = 'RIGHT';
        });

        setInterval(() => direction = newDirection, 100);
        gameLoop();
    </script>
</body>
</html>

