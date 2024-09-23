---
layout: page
title: Cookie Clicker!!
description: The cookie clicker game
permalink: /cookieclicker/
---

<style>
    body {
        font-family: Arial, sans-serif;
        background-color: #f8f9fa;
        text-align: center;
    }
    .cookie-container {
        margin: 20px auto;
        width: 200px;
        height: 200px;
        background-image: url('https://example.com/cookie.png'); /* Replace with your cookie image URL */
        background-size: cover;
        cursor: pointer;
        border-radius: 50%;
        box-shadow: 0 0 15px rgba(0, 0, 0, 0.3);
        transition: transform 0.2s;
    }
    .cookie-container:hover {
        transform: scale(1.1);
    }
    .stats, .shop {
        margin: 20px;
    }
    button {
        padding: 10px 20px;
        margin: 10px;
        font-size: 16px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s;
    }
    button:hover {
        background-color: #e0e0e0;
    }
    .reset-button {
        background-color: #ff4d4d;
        color: white;
    }
</style>

<h1>Enhanced Cookie Clicker</h1>

<div class="cookie-container" id="cookie" onclick="clickCookie()"></div>

<div class="stats">
    <p>🍪 Cookies: <span id="cookieCount">0</span></p>
    <p>🚀 Cookies per second: <span id="cookiesPerSecond">0</span></p>
    <p>⭐ Score Multiplier: <span id="multiplier">1</span></p>
</div>

<div class="shop">
    <h2>Shop Upgrades</h2>
    <button id="upgrade1" onclick="buyUpgrade(1)">+1 Cookie per Second (Cost: 50 cookies)</button>
    <button id="upgrade2" onclick="buyUpgrade(2)">+5 Cookies per Second (Cost: 200 cookies)</button>
    <button id="upgrade3" onclick="buyUpgrade(3)">+10 Cookies per Second (Cost: 500 cookies)</button>
    <button onclick="applyMultiplier()">Apply Multiplier (Cost: 100 cookies)</button>
    <button class="reset-button" onclick="resetGame()">Reset Game</button>
</div>

<script>
    let cookies = 0;
    let cookiesPerSecond = 0;
    let scoreMultiplier = 1;

    function clickCookie() {
        cookies += scoreMultiplier; // Increment by multiplier
        updateDisplay();
        updateButtons();
        animateCookie();
    }

    function buyUpgrade(upgrade) {
        if (upgrade === 1 && cookies >= 50) {
            cookies -= 50;
            cookiesPerSecond += 1;
        } else if (upgrade === 2 && cookies >= 200) {
            cookies -= 200;
            cookiesPerSecond += 5;
        } else if (upgrade === 3 && cookies >= 500) {
            cookies -= 500;
            cookiesPerSecond += 10;
        }
        updateDisplay();
        updateButtons();
    }

    function applyMultiplier() {
        if (cookies >= 100) {
            cookies -= 100;
            scoreMultiplier++;
            updateDisplay();
        }
    }

    function updateDisplay() {
        document.getElementById('cookieCount').innerText = cookies;
        document.getElementById('cookiesPerSecond').innerText = cookiesPerSecond;
        document.getElementById('multiplier').innerText = scoreMultiplier;
    }

    function updateButtons() {
        document.getElementById('upgrade1').disabled = cookies < 50;
        document.getElementById('upgrade2').disabled = cookies < 200;
        document.getElementById('upgrade3').disabled = cookies < 500;
    }

    function autoGenerateCookies() {
        cookies += cookiesPerSecond;
        updateDisplay();
        updateButtons();
    }

    function animateCookie() {
        const cookie = document.getElementById('cookie');
        cookie.style.transform = "scale(1.2)";
        setTimeout(() => {
            cookie.style.transform = "scale(1)";
        }, 200);
    }

    function resetGame() {
        cookies = 0;
        cookiesPerSecond = 0;
        scoreMultiplier = 1;
        updateDisplay();
        updateButtons();
    }

    setInterval(autoGenerateCookies, 1000);
</script>

