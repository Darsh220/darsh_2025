---
layout: page
title: Cookie Clicker!!
permalink: /cookieclicker/
---

<style>
  .cookie {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    background-color: #deb887;
    display: inline-block;
    cursor: pointer;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  }

  .stats {
    margin: 20px;
    font-size: 18px;
  }

  .shop {
    margin: 30px auto;
    padding: 20px;
    width: 300px;
    background-color: #fff;
    border: 2px solid #ddd;
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  }

  .shop button {
    display: block;
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    border: none;
    border-radius: 5px;
    background-color: #4caf50;
    color: white;
    font-size: 16px;
    cursor: pointer;
  }

  .shop button:disabled {
    background-color: #ccc;
  }
</style>

<div>
  <h1>Cookie Clicker</h1>
  
  <div class="cookie" id="cookie" onclick="clickCookie()"></div>
  
  <div class="stats">
    <p>Cookies: <span id="cookieCount">0</span></p>
    <p>Cookies per second: <span id="cookiesPerSecond">0</span></p>
  </div>

  <div class="shop">
    <h2>Shop</h2>
    <button id="upgrade1" onclick="buyUpgrade(1)">Buy +1 Cookie per Second (Cost: 50 cookies)</button>
    <button id="upgrade2" onclick="buyUpgrade(2)">Buy +5 Cookies per Second (Cost: 200 cookies)</button>
    <button id="upgrade3" onclick="buyUpgrade(3)">Buy +10 Cookies per Second (Cost: 500 cookies)</button>
  </div>
</div>

<script>
  let cookies = 0;
  let cookiesPerSecond = 0;

  function clickCookie() {
    cookies++;
    updateDisplay();
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

  function updateDisplay() {
    document.getElementById('cookieCount').innerText = cookies;
    document.getElementById('cookiesPerSecond').innerText = cookiesPerSecond;
  }

  function updateButtons() {
    document.getElementById('upgrade1').disabled = cookies < 50;
    document.getElementById('upgrade2').disabled = cookies < 200;
    document.getElementById('upgrade3').disabled = cookies < 500;
  }

  function autoGenerateCookies() {
    cookies += cookiesPerSecond;
    updateDisplay();
  }

  setInterval(autoGenerateCookies, 1000); // Cookies generated per second
</script>
