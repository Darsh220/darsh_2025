---
layout: post
title: Github Playground
description: Github Playground
courses: {'csp': {'week': 1}}
comments: True
sticky_rank: 1
---

```python
from newspaper import Article
from IPython.display import display, Markdown


urls = ["http://cnn.com/2023/03/29/entertainment/the-mandalorian-episode-5-recap/index.html", 
        "https://www.cnn.com/2023/06/09/entertainment/jurassic-park-anniversary/index.html"]

for url in urls:
    article = Article(url)
    article.download()
    article.parse()
   
    display(Markdown(article.title)) 
    display(Markdown(article.text)) 
    print("\n")
```


‘The Mandalorian’ finally comes into focus, while giving out a ‘Rebels’ yell



Editor’s Note: The following contains spoilers about the fifth episode of “The Mandalorian,” Season 3, “The Pirate.”

CNN —

After what can at best be described as a somewhat disjointed third season thus far, the fifth episode of “The Mandalorian” began to bring those pieces together and into focus, while continuing to draw upon the “Star Wars” animated series that preceded it, including another cameo by a character from the rightfully lauded “Rebels.”

Subtitled “The Pirate,” the episode presented further evidence of the dysfunctional nature of the New Republic, unable or unwilling to defend a faraway planet from an invading band of pirates. (Lucasfilm being a unit of Disney, the marauders had a certain “Yo ho, yo ho” vibe to them.)

The siege also played into Mandalorian politics, and the efforts of Bo-Katan (Katee Sackhoff) to reclaim her heritage and potentially reunite her people’s various tribes, after leading them, along with Din Djarin (voiced by Pedro Pascal), to the rescue of his pal Greef Karga (Carl Weathers) and the planet’s residents.

Still, the most pleasing moment for longtime “Star Wars” fans was likely what amounted to a throwaway scene, introducing a live-action version of the hulking alien Zeb, a character from the animated “Star Wars Rebels,” which concluded in 2018. “The Mandalorian” has drawn heavily from those properties, which were overseen by one of its executive producers, Dave Filoni. (In another nice touch, Steve Blum again provided the voice of the character, and Zeb looked a whole lot better than the pirate leader.)

Finally, the episode closed with evidence that the evil Moff Gideon (played by Giancarlo Esposito previously) had seemingly been freed from the prison ship that was transporting him to stand trial, reviving that potential threat.

Having resolved the fate of Grogu, a.k.a. Baby Yoda, during the first two seasons, “The Mandalorian” has thus moved on to fill in narrative gaps about an under-explored chapter in “Star Wars” history – namely, the factors that resulted in the fall of the New Republic and the rise of the First Order, the plot line featured in the most recent trilogy that began with “The Force Awakens.”

“This isn’t a rebellion anymore,” a bureaucrat (played by Tim Meadows) says about what happens outside of the New Republic’s jurisdiction, conveying an indifference to the fate of the planet Nevarro overtly articulated later when it was observed that the governing body in Coruscant “doesn’t care.”

Executive producers Jon Favreau and Filoni have taken their time in reaching this point, juggling these various issues in somewhat ungainly fashion through the first half of the season. That perhaps reflects the transition of the show to an emphasis on the macro instead of the micro, while still finding time to detour for the occasional “Rebels” yell.


    
    



‘Jurassic Park’ still has bite at 30 years old, and here’s why



CNN —

It’s been 30 years since Steven Spielberg’s dinosaurs stampeded across the screen in the first “Jurassic Park,” but it feels more recent.

I was 12 in June of 1993 and vividly remember watching with glee when the Tyrannosaurus Rex, with its teeny arms and perpetual scowl, blew the walls of the bathroom down like a big bad wolf and promptly ate the lawyer character (played to hilarious effect by Martin Ferrero). Part of this, surely, had to do with the fact that I was a mouthy pre-teen, and many adults in my sphere at the time opined that I “would make a great lawyer” just like my father – a fate I abhorred.

Admittedly, I was the exact target audience for this creature feature, and even though I was already somewhat of a self-taught critic (note the aforementioned mouthiness), I was awed by what I saw that summer three decades ago, and my impressions of “Jurassic Park” remain to this day.

Joseph Mazzello in "Jurassic Park." Amblin/Universal/Kobal/Shutterstock

Part of that lasting impact, of course, has to do with the still-groundbreaking effects in the movie, which surprisingly hold up, and on a fairly hi-tech 72-inch TV screen to boot. While the first dino money shot – of the plant-eating brachiosaurus – might look just a tad soupy in 2023, it still looks considerably better than more contemporary fare, and the ensuing imagery of the more predatory beasts (like T-rex and especially those raptors) remains top-notch. The computer-generated imagery in the movie is essentially credited with marking the end of stop-motion animation as the go-to effects option for films such as these, notably used in everything that came before, from 1933’s “King Kong” to 1981’s “Clash of the Titans.” The animatronics are something to behold as well, particularly the ailing triceratops responsible for that “one big pile of s—,” one of many priceless quips uttered by Ian Malcolm (Jeff Goldblum).

The appeal of “Jurassic,” based on Michael Crichton’s acclaimed novel, is also largely due to the film’s suspenseful and pared-down pacing, which of course can be linked to Spielberg, who learned a thing or two about keeping his cards close to his chest with “Jaws” – the great white mother of all creature features that famously showed startlingly little of the big fish before the climax.

Another “Jaws” connection is prolific film composer John Williams, the Spielberg collaborator who created a majestic score for “Jurassic Park” that is still synonymous with an air of discovery, one that can easily be hummed when looking upon any great view or upon entering a new and uncharted space.

Laura Dern, Sam Neill and Joseph Mazzello in "Jurassic Park." Amblin/Universal/Kobal/Shutterstock

And then there’s the casting, an element that sometimes takes a number of years to truly appreciate. Aside from the always-dependable Goldblum, there’s Laura Dern, who carved out her own Sigourney Weaver-shaped notch in the movie thanks to that one terrifying sequence in the control shed. Plus, her reaction shot to that first dinosaur reveal – along with that of Sam Neill – could be viewed as a textbook for green-screen acting, which has become the standard ever since, in Marvel movies and beyond. Add to that the amazing and meme-worthy smaller performances from Samuel L. Jackson (“Hold onto your butts!”), Wayne Knight (“Ah ah ah! You didn’t say the magic word!”) and Bob Peck (“Clever girl”), and you’ve got a crowd-pleaser that is equal parts adventure, comedy and chomp-chomp thriller.

While the rest of the entries in the “Jurassic” franchise have not exactly been up to par (aside from 2015’s not-terrible first reboot “Jurassic World”), the original flick still “rules” – and is definitely worth a rewatch on the occasion of its 30th birthday.


    
    



```python
import sys
from typing import Union

Number = Union[int, float]  
Numbers = list[Number] 
Scores = Union[Number, Numbers]  

def mean(scores: Scores, method: int = 1) -> float:
    """
    Calculate the mean of a list of scores.
    
    Average and Average2 are hidden functions performing mean algorithm

    If a single score is provided in scores, it is returned as the mean.
    If a list of scores is provided, the average is calculated and returned.
    """
    
    def average(scores): 
        """Calculate the average of a list of scores using a Python for loop with rounding."""
        sum = 0
        len = 0
        for score in scores:
            if isinstance(score, Number):
                sum += score
                len += 1
            else:
                print("Bad data: " + str(score) + " in " + str(scores))
                sys.exit()
        return sum / len
    
    def average2(scores):
        """Calculate the average of a list of scores using the built-in sum() function with rounding."""
        return sum(scores) / len(scores)

    
    if isinstance(scores, list):
        if method == 1:  
           result = average(scores)
        else:
            result = average2(scores)
        return round(result + 0.005, 2)
    return scores 


singleScore = 100
print("Print test data: " + str(singleScore))  
print("Mean of single number: " + str(mean(singleScore)))

print()
testScores = [90.5, 100, 85.4, 88]
print("Print test data: " + str(testScores))
print("Average score, loop method: " + str(mean(testScores)))
print("Average score, function method: " +  str(mean(testScores, 2)))

print()

badData = [100, "NaN", 90]
print("Print test data: " + str(badData))
print("Mean with bad data: " + str(mean(badData)))
```

    Print test data: 100
    Mean of single number: 100
    
    Print test data: [90.5, 100, 85.4, 88]
    Average score, loop method: 90.98
    Average score, function method: 90.98
    
    Print test data: [100, 'NaN', 90]
    Bad data: NaN in [100, 'NaN', 90]



    An exception has occurred, use %tb to see the full traceback.


    SystemExit



    /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/IPython/core/interactiveshell.py:3585: UserWarning: To exit: use 'exit', 'quit', or Ctrl-D.
      warn("To exit: use 'exit', 'quit', or Ctrl-D.", stacklevel=1)



```python
from IPython.core.display import display, HTML


html_code = """
<h2>Color Picker</h2>
<input type="color" id="colorPicker" onchange="changeColor()">
<p>Selected Color: <span id="colorValue">#ffffff</span></p>

<div id="colorDisplay" style="width: 100%; height: 100px; border: 1px solid #000;"></div>

<style>
    body { font-family: Arial, sans-serif; }
    #colorDisplay {
        transition: background-color 0.3s ease;
    }
</style>

<script>
    function changeColor() {
        const color = document.getElementById('colorPicker').value;
        document.getElementById('colorValue').innerText = color;
        document.getElementById('colorDisplay').style.backgroundColor = color;
    }
</script>
"""


display(HTML(html_code))

```

    /tmp/ipykernel_4493/2962417301.py:1: DeprecationWarning: Importing display from IPython.core.display is deprecated since IPython 7.14, please import from IPython display
      from IPython.core.display import display, HTML




<h2>Color Picker</h2>
<input type="color" id="colorPicker" onchange="changeColor()">
<p>Selected Color: <span id="colorValue">#ffffff</span></p>

<div id="colorDisplay" style="width: 100%; height: 100px; border: 1px solid #000;"></div>

<style>
    body { font-family: Arial, sans-serif; }
    #colorDisplay {
        transition: background-color 0.3s ease;
    }
</style>

<script>
    function changeColor() {
        const color = document.getElementById('colorPicker').value;
        document.getElementById('colorValue').innerText = color;
        document.getElementById('colorDisplay').style.backgroundColor = color;
    }
</script>




```python
from IPython.core.display import display, HTML


html_code = """
<h2>Theme Toggle</h2>
<button class="theme-button" onclick="toggleTheme()">Toggle Theme</button>

<p>This is a simple theme toggle example. Click the button to change the theme!</p>

<style>
    body {
        font-family: Arial, sans-serif;
        transition: background-color 0.3s, color 0.3s;
    }
    .light {
        background-color: white;
        color: black;
    }
    .dark {
        background-color: #333;
        color: white;
    }
    .theme-button {
        background-color: lightblue;
        color: white;
        padding: 10px 15px;
        margin: 5px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    .theme-button:hover {
        background-color: #45a049;
    }
</style>

<script>
    let isDarkTheme = false;

    function toggleTheme() {
        isDarkTheme = !isDarkTheme;
        document.body.className = isDarkTheme ? 'dark' : 'light';
    }

    
    document.body.className = 'light';
</script>
"""


display(HTML(html_code))

```

    /tmp/ipykernel_80268/3105715442.py:1: DeprecationWarning: Importing display from IPython.core.display is deprecated since IPython 7.14, please import from IPython display
      from IPython.core.display import display, HTML




<h2>Theme Toggle</h2>
<button class="theme-button" onclick="toggleTheme()">Toggle Theme</button>

<p>This is a simple theme toggle example. Click the button to change the theme!</p>

<style>
    body {
        font-family: Arial, sans-serif;
        transition: background-color 0.3s, color 0.3s;
    }
    .light {
        background-color: white;
        color: black;
    }
    .dark {
        background-color: #333;
        color: white;
    }
    .theme-button {
        background-color: lightblue;
        color: white;
        padding: 10px 15px;
        margin: 5px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    .theme-button:hover {
        background-color: #45a049;
    }
</style>

<script>
    let isDarkTheme = false;

    function toggleTheme() {
        isDarkTheme = !isDarkTheme;
        document.body.className = isDarkTheme ? 'dark' : 'light';
    }


    document.body.className = 'light';
</script>




```python

```
