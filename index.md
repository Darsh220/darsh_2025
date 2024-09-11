---
layout: base
title: Student Home 
description: Home Page
hide: true
---

This is my page 
<img src="https://media.tenor.com/WuNndB5UddwAAAAM/mario-monday.gif" alt="MARIO GIF">

---
layout: default
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Mario</title>
    <style>
        #mario {
            width: 100px;
            height: 100px;
            background-image: url('/assets/mario.png');
            background-size: cover;
            position: relative;
            transition: left 0.2s;
        }
        body {
            margin: 0;
            padding: 0;
            overflow: hidden;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background-color: #87CEEB; /* Light sky blue background */
        }
    </style>
</head>
<body>
    <div id="mario"></div>

    <script>
        document.addEventListener('keydown', function(event) {
            var mario = document.getElementById('mario');
            var marioStyle = window.getComputedStyle(mario);
            var left = parseInt(marioStyle.left, 10) || 0;

            switch (event.key) {
                case 'ArrowRight':
                    mario.style.left = (left + 10) + 'px';
                    break;
                case 'ArrowLeft':
                    mario.style.left = (left - 10) + 'px';
                    break;
            }
        });
    </script>
</body>
</html>
