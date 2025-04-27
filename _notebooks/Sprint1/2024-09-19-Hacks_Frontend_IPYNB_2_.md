---
layout: post
title: Frontend
description: Jupyter notebooks and Python
courses: {'csp': {'week': 1}}
comments: True
sticky_rank: 1
---

```python
pip install ipywidgets

```

    Requirement already satisfied: ipywidgets in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (8.1.5)
    Requirement already satisfied: comm>=0.1.3 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipywidgets) (0.2.2)
    Requirement already satisfied: ipython>=6.1.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipywidgets) (8.27.0)
    Requirement already satisfied: traitlets>=4.3.1 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipywidgets) (5.14.3)
    Requirement already satisfied: widgetsnbextension~=4.0.12 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipywidgets) (4.0.13)
    Requirement already satisfied: jupyterlab-widgets~=3.0.12 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipywidgets) (3.0.13)
    Requirement already satisfied: decorator in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipython>=6.1.0->ipywidgets) (5.1.1)
    Requirement already satisfied: jedi>=0.16 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipython>=6.1.0->ipywidgets) (0.19.1)
    Requirement already satisfied: matplotlib-inline in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipython>=6.1.0->ipywidgets) (0.1.7)
    Requirement already satisfied: prompt-toolkit<3.1.0,>=3.0.41 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipython>=6.1.0->ipywidgets) (3.0.47)
    Requirement already satisfied: pygments>=2.4.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipython>=6.1.0->ipywidgets) (2.18.0)
    Requirement already satisfied: stack-data in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipython>=6.1.0->ipywidgets) (0.6.3)
    Requirement already satisfied: pexpect>4.3 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from ipython>=6.1.0->ipywidgets) (4.9.0)
    Requirement already satisfied: parso<0.9.0,>=0.8.3 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from jedi>=0.16->ipython>=6.1.0->ipywidgets) (0.8.4)
    Requirement already satisfied: ptyprocess>=0.5 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from pexpect>4.3->ipython>=6.1.0->ipywidgets) (0.7.0)
    Requirement already satisfied: wcwidth in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from prompt-toolkit<3.1.0,>=3.0.41->ipython>=6.1.0->ipywidgets) (0.2.13)
    Requirement already satisfied: executing>=1.2.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from stack-data->ipython>=6.1.0->ipywidgets) (2.1.0)
    Requirement already satisfied: asttokens>=2.1.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from stack-data->ipython>=6.1.0->ipywidgets) (2.4.1)
    Requirement already satisfied: pure-eval in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from stack-data->ipython>=6.1.0->ipywidgets) (0.2.3)
    Requirement already satisfied: six>=1.12.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from asttokens>=2.1.0->stack-data->ipython>=6.1.0->ipywidgets) (1.16.0)
    Note: you may need to restart the kernel to use updated packages.



```python
from IPython.core.display import display, HTML

html_code = """
<h2>User Information</h2>
<div class="form-group">
    <label for="name">Name:</label>
    <input type="text" id="name" placeholder="Enter your name">
</div>
<div class="form-group">
    <label for="age">Age:</label>
    <input type="number" id="age" min="0" max="100">
</div>
<div class="form-group">
    <label for="hobby">Hobby:</label>
    <select id="hobby">
        <option>Select a hobby</option>
        <option>Reading</option>
        <option>Traveling</option>
        <option>Sports</option>
        <option>Cooking</option>
    </select>
</div>
<div class="form-group">
    <label>
        <input type="checkbox" id="subscribe"> Subscribe to newsletter
    </label>
</div>
<button class="my-button" onclick="submitForm()">Submit</button>

<div id="output"></div>

<style>
    .form-group { margin: 10px 0; }
    .my-button {
        background-color: lightblue;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    .my-button:hover {
        background-color: #45a049;
    }
</style>

<script>
    function submitForm() {
        const name = document.getElementById('name').value;
        const age = document.getElementById('age').value;
        const hobby = document.getElementById('hobby').value;
        const subscribe = document.getElementById('subscribe').checked;

        let output = `<h3>Hello, ${name}!</h3>`;
        output += `<p>You are ${age} years old.</p>`;
        output += `<p>Your hobby is: ${hobby === 'Select a hobby' ? 'Not selected' : hobby}.</p>`;
        output += `<p>Newsletter Subscription: ${subscribe ? 'Yes' : 'No'}</p>`;

        document.getElementById('output').innerHTML = output;
    }
</script>
"""
display(HTML(html_code))

```

    /tmp/ipykernel_114687/2581505164.py:1: DeprecationWarning: Importing display from IPython.core.display is deprecated since IPython 7.14, please import from IPython display
      from IPython.core.display import display, HTML




<h2>User Information</h2>
<div class="form-group">
    <label for="name">Name:</label>
    <input type="text" id="name" placeholder="Enter your name">
</div>
<div class="form-group">
    <label for="age">Age:</label>
    <input type="number" id="age" min="0" max="100">
</div>
<div class="form-group">
    <label for="hobby">Hobby:</label>
    <select id="hobby">
        <option>Select a hobby</option>
        <option>Reading</option>
        <option>Traveling</option>
        <option>Sports</option>
        <option>Cooking</option>
    </select>
</div>
<div class="form-group">
    <label>
        <input type="checkbox" id="subscribe"> Subscribe to newsletter
    </label>
</div>
<button class="my-button" onclick="submitForm()">Submit</button>

<div id="output"></div>

<style>
    .form-group { margin: 10px 0; }
    .my-button {
        background-color: lightblue;
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    .my-button:hover {
        background-color: #45a049;
    }
</style>

<script>
    function submitForm() {
        const name = document.getElementById('name').value;
        const age = document.getElementById('age').value;
        const hobby = document.getElementById('hobby').value;
        const subscribe = document.getElementById('subscribe').checked;

        let output = `<h3>Hello, ${name}!</h3>`;
        output += `<p>You are ${age} years old.</p>`;
        output += `<p>Your hobby is: ${hobby === 'Select a hobby' ? 'Not selected' : hobby}.</p>`;
        output += `<p>Newsletter Subscription: ${subscribe ? 'Yes' : 'No'}</p>`;

        document.getElementById('output').innerHTML = output;
    }
</script>




```python
from IPython.core.display import display, HTML

html_code = """
<h2>Simple Calculator</h2>
<div>
    <input type="text" id="num1" placeholder="Enter first number">
    <input type="text" id="num2" placeholder="Enter second number">
</div>
<div>
    <button class="calc-button" onclick="calculate('+')">+</button>
    <button class="calc-button" onclick="calculate('-')">-</button>
    <button class="calc-button" onclick="calculate('*')">*</button>
    <button class="calc-button" onclick="calculate('/')">/</button>
</div>

<h3>Result: <span id="result">0</span></h3>

<style>
    body { font-family: Arial, sans-serif; }
    .calc-button {
        background-color: lightblue;
        color: white;
        padding: 10px 15px;
        margin: 5px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    .calc-button:hover {
        background-color: #45a049;
    }
</style>

<script>
    function calculate(operator) {
        const num1 = parseFloat(document.getElementById('num1').value);
        const num2 = parseFloat(document.getElementById('num2').value);
        let result;

        if (operator === '+') {
            result = num1 + num2;
        } else if (operator === '-') {
            result = num1 - num2;
        } else if (operator === '*') {
            result = num1 * num2;
        } else if (operator === '/') {
            result = num2 !== 0 ? num1 / num2 : 'Cannot divide by zero';
        }

        document.getElementById('result').innerText = result || 0;
    }
</script>
"""
display(HTML(html_code))

```

    /tmp/ipykernel_114687/1278385433.py:1: DeprecationWarning: Importing display from IPython.core.display is deprecated since IPython 7.14, please import from IPython display
      from IPython.core.display import display, HTML




<h2>Simple Calculator</h2>
<div>
    <input type="text" id="num1" placeholder="Enter first number">
    <input type="text" id="num2" placeholder="Enter second number">
</div>
<div>
    <button class="calc-button" onclick="calculate('+')">+</button>
    <button class="calc-button" onclick="calculate('-')">-</button>
    <button class="calc-button" onclick="calculate('*')">*</button>
    <button class="calc-button" onclick="calculate('/')">/</button>
</div>

<h3>Result: <span id="result">0</span></h3>

<style>
    body { font-family: Arial, sans-serif; }
    .calc-button {
        background-color: lightblue;
        color: white;
        padding: 10px 15px;
        margin: 5px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    .calc-button:hover {
        background-color: #45a049;
    }
</style>

<script>
    function calculate(operator) {
        const num1 = parseFloat(document.getElementById('num1').value);
        const num2 = parseFloat(document.getElementById('num2').value);
        let result;

        if (operator === '+') {
            result = num1 + num2;
        } else if (operator === '-') {
            result = num1 - num2;
        } else if (operator === '*') {
            result = num1 * num2;
        } else if (operator === '/') {
            result = num2 !== 0 ? num1 / num2 : 'Cannot divide by zero';
        }

        document.getElementById('result').innerText = result || 0;
    }
</script>




```python
from IPython.core.display import display, HTML

html_code = """
<h2>Watch Tutorial</h2>
<button class="youtube-button" onclick="window.open('https://www.youtube.com/watch?v=YOUR_VIDEO_ID', '_blank')">Watch Video</button>

<style>
    body { font-family: Arial, sans-serif; }
    .youtube-button {
        background-color: lightblue;
        color: white;
        padding: 10px 15px;
        margin: 5px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    .youtube-button:hover {
        background-color: #45a049;
    }
</style>
"""
display(HTML(html_code))

```

    /tmp/ipykernel_114687/3794460850.py:1: DeprecationWarning: Importing display from IPython.core.display is deprecated since IPython 7.14, please import from IPython display
      from IPython.core.display import display, HTML




<h2>Watch Tutorial</h2>
<button class="youtube-button" onclick="window.open('https://www.youtube.com/watch?v=YOUR_VIDEO_ID', '_blank')">Watch Video</button>

<style>
    body { font-family: Arial, sans-serif; }
    .youtube-button {
        background-color: lightblue;
        color: white;
        padding: 10px 15px;
        margin: 5px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    .youtube-button:hover {
        background-color: #45a049;
    }
</style>




```python
%%html
<div>
    <p style="border: 4px solid #ff0000; color: #FFFF; paddding: 12px; border-radius: 5px;">
                                                                                        paragraph
    </p>
     
    <button class="cta">
        <span>Button</span>
         <svg width="15px" height="10px" viewBox="0 0 13 10">
        <path d="M1,5 L11,5"></path>
        <polyline points="8 1 12 5 8 9"></polyline>
        </svg>
    </button>

</div>

<div style="margin-top: 22px;">
    <style>
.cta {
    position: relative;
    margin: auto;
    padding: 12px 18px;
    transition: all 0.2s ease;
    border: none;
    background: none;
    cursor: pointer;
  }
  
  .cta:before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    display: block;
    border-radius: 50px;
    background: #b1dae7;
    width: 45px;
    height: 45px;
    transition: all 0.3s ease;
  }
  
  .cta span {
    position: relative;
    font-family: "Ubuntu", sans-serif;
    font-size: 18px;
    font-weight: 700;
    letter-spacing: 0.05em;
    color: #234567;
  }
  
  .cta svg {
    position: relative;
    top: 0;
    margin-left: 10px;
    fill: none;
    stroke-linecap: round;
    stroke-linejoin: round;
    stroke: #234567;
    stroke-width: 2;
    transform: translateX(-5px);
    transition: all 0.3s ease;
  }
  
  .cta:hover:before {
    width: 100%;
    background: #b1dae7;
  }
  
  .cta:hover svg {
    transform: translateX(0);
  }
  
  .cta:active {
    transform: scale(0.95);
  }
  
    </style>

    <a href="https://example.com/" style="border: 2px solid #1E90FF; color: #1E90FF; display: block; padding: 10px; border-radius: 5px; text-align: center; margin-bottom: 10px; text-decoration: none;">
        A
    </a>
    <a href="https://example.com/" style="border: 2px solid #1f8efd; color: #1E90FF; display: block; padding: 10px; border-radius: 5px; text-align: center; margin-bottom: 10px; text-decoration: none;">
        A
    </a>
    <p style="border: 4px solid #ff0000; color: #FFFF; paddding: 12px; border-radius: 5px;">  
        paragraph
    </p>
</div>

```




<div>
    <p style="border: 4px solid #ff0000; color: #FFFF; paddding: 12px; border-radius: 5px;">
                                                                                        paragraph
    </p>

    <button class="cta">
        <span>Button</span>
         <svg width="15px" height="10px" viewBox="0 0 13 10">
        <path d="M1,5 L11,5"></path>
        <polyline points="8 1 12 5 8 9"></polyline>
        </svg>
    </button>

</div>

<div style="margin-top: 22px;">
    <style>
.cta {
    position: relative;
    margin: auto;
    padding: 12px 18px;
    transition: all 0.2s ease;
    border: none;
    background: none;
    cursor: pointer;
  }

  .cta:before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    display: block;
    border-radius: 50px;
    background: #b1dae7;
    width: 45px;
    height: 45px;
    transition: all 0.3s ease;
  }

  .cta span {
    position: relative;
    font-family: "Ubuntu", sans-serif;
    font-size: 18px;
    font-weight: 700;
    letter-spacing: 0.05em;
    color: #234567;
  }

  .cta svg {
    position: relative;
    top: 0;
    margin-left: 10px;
    fill: none;
    stroke-linecap: round;
    stroke-linejoin: round;
    stroke: #234567;
    stroke-width: 2;
    transform: translateX(-5px);
    transition: all 0.3s ease;
  }

  .cta:hover:before {
    width: 100%;
    background: #b1dae7;
  }

  .cta:hover svg {
    transform: translateX(0);
  }

  .cta:active {
    transform: scale(0.95);
  }

    </style>

    <a href="https://example.com/" style="border: 2px solid #1E90FF; color: #1E90FF; display: block; padding: 10px; border-radius: 5px; text-align: center; margin-bottom: 10px; text-decoration: none;">
        A
    </a>
    <a href="https://example.com/" style="border: 2px solid #1f8efd; color: #1E90FF; display: block; padding: 10px; border-radius: 5px; text-align: center; margin-bottom: 10px; text-decoration: none;">
        A
    </a>
    <p style="border: 4px solid #ff0000; color: #FFFF; paddding: 12px; border-radius: 5px;">  
        paragraph
    </p>
</div>


