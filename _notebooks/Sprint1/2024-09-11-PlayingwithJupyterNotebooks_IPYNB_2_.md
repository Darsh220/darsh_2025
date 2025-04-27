---
layout: post
title: Playing With Hacks
description: Jupyter notebooks and Python
courses: {'csp': {'week': 1}}
comments: True
sticky_rank: 1
---

```python
print("hello world")
```

    hello world



```python
!pip install wikipedia
```

    Requirement already satisfied: wikipedia in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (1.4.0)
    Requirement already satisfied: beautifulsoup4 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from wikipedia) (4.12.3)
    Requirement already satisfied: requests<3.0.0,>=2.0.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from wikipedia) (2.32.3)
    Requirement already satisfied: charset-normalizer<4,>=2 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from requests<3.0.0,>=2.0.0->wikipedia) (3.3.2)
    Requirement already satisfied: idna<4,>=2.5 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from requests<3.0.0,>=2.0.0->wikipedia) (3.8)
    Requirement already satisfied: urllib3<3,>=1.21.1 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from requests<3.0.0,>=2.0.0->wikipedia) (2.2.2)
    Requirement already satisfied: certifi>=2017.4.17 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from requests<3.0.0,>=2.0.0->wikipedia) (2024.8.30)
    Requirement already satisfied: soupsieve>1.2 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from beautifulsoup4->wikipedia) (2.6)



```python
import wikipedia
from IPython.display import display, Markdown

print("Welcome to Wikipedia!")
search_history = []
condition = True
while condition:
    search_input = input("Enter a search or type 'quit' to exit: ")
    if search_input != "quit":
            result = wikipedia.search(search_input)
            # Get the summary of the first result
            summary = wikipedia.summary(result[0])
            print(search_input)
            search_history.append(search_input)
            # print(summary) # console display
            display(Markdown(summary)) # Jupyter display
    else:
        condition = False
        print(f"Here is your search history: {search_history}")
        choice = input("Would you like to clear your search history? [y/n]")
        if choice == "y":
            search_history.clear()
            print("Search history cleared!")
            print(search_history)
        elif choice == "n":
            print("Ok, no problem.")
        else:
            print("Invalid choice entered.")
        print("Thank you for visiting Wikipedia! Come back soon!")
```

    Welcome to Wikipedia!


    /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/wikipedia/wikipedia.py:389: GuessedAtParserWarning: No parser was explicitly specified, so I'm using the best available HTML parser for this system ("lxml"). This usually isn't a problem, but if you run this code on another system, or in a different virtual environment, it may use a different parser and behave differently.
    
    The code that caused this warning is on line 389 of the file /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/wikipedia/wikipedia.py. To get rid of this warning, pass the additional argument 'features="lxml"' to the BeautifulSoup constructor.
    
      lis = BeautifulSoup(html).find_all('li')



    ---------------------------------------------------------------------------

    DisambiguationError                       Traceback (most recent call last)

    Cell In[1], line 12
         10 result = wikipedia.search(search_input)
         11 # Get the summary of the first result
    ---> 12 summary = wikipedia.summary(result[0])
         13 print(search_input)
         14 search_history.append(search_input)


    File ~/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/wikipedia/util.py:28, in cache.__call__(self, *args, **kwargs)
         26   ret = self._cache[key]
         27 else:
    ---> 28   ret = self._cache[key] = self.fn(*args, **kwargs)
         30 return ret


    File ~/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/wikipedia/wikipedia.py:231, in summary(title, sentences, chars, auto_suggest, redirect)
        216 '''
        217 Plain text summary of the page.
        218 
       (...)
        226 * redirect - allow redirection without raising RedirectError
        227 '''
        229 # use auto_suggest and redirect to get the correct article
        230 # also, use page's error checking to raise DisambiguationError if necessary
    --> 231 page_info = page(title, auto_suggest=auto_suggest, redirect=redirect)
        232 title = page_info.title
        233 pageid = page_info.pageid


    File ~/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/wikipedia/wikipedia.py:276, in page(title, pageid, auto_suggest, redirect, preload)
        273     except IndexError:
        274       # if there is no suggestion or search results, the page doesn't exist
        275       raise PageError(title)
    --> 276   return WikipediaPage(title, redirect=redirect, preload=preload)
        277 elif pageid is not None:
        278   return WikipediaPage(pageid=pageid, preload=preload)


    File ~/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/wikipedia/wikipedia.py:299, in WikipediaPage.__init__(self, title, pageid, redirect, preload, original_title)
        296 else:
        297   raise ValueError("Either a title or a pageid must be specified")
    --> 299 self.__load(redirect=redirect, preload=preload)
        301 if preload:
        302   for prop in ('content', 'summary', 'images', 'references', 'links', 'sections'):


    File ~/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/wikipedia/wikipedia.py:393, in WikipediaPage.__load(self, redirect, preload)
        390   filtered_lis = [li for li in lis if not 'tocsection' in ''.join(li.get('class', []))]
        391   may_refer_to = [li.a.get_text() for li in filtered_lis if li.a]
    --> 393   raise DisambiguationError(getattr(self, 'title', page['title']), may_refer_to)
        395 else:
        396   self.pageid = pageid


    DisambiguationError: "can" may refer to: 
    Aluminum can
    Drink can
    Oil can
    Steel and tin cans
    Trash can
    Petrol can
    Can (band)
    Can (album)
    Can (South Korean band)
    Canada
    Cantoris
    Can (name)
    Can (verb)
    Canning
    River Can
    Tomato can (sports idiom)
    CAN (disambiguation)
    Cann (disambiguation)
    Cans (disambiguation)
    Kan (disambiguation)



```python
!pip install newspaper3k
```

    Requirement already satisfied: newspaper3k in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (0.2.8)
    Requirement already satisfied: beautifulsoup4>=4.4.1 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (4.12.3)
    Requirement already satisfied: Pillow>=3.3.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (10.4.0)
    Requirement already satisfied: PyYAML>=3.11 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (6.0.2)
    Requirement already satisfied: cssselect>=0.9.2 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (1.2.0)
    Requirement already satisfied: lxml>=3.6.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (5.3.0)
    Requirement already satisfied: nltk>=3.2.1 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (3.9.1)
    Requirement already satisfied: requests>=2.10.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (2.32.3)
    Requirement already satisfied: feedparser>=5.2.1 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (6.0.11)
    Requirement already satisfied: tldextract>=2.0.1 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (5.1.2)
    Requirement already satisfied: feedfinder2>=0.0.4 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (0.0.4)
    Requirement already satisfied: jieba3k>=0.35.1 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (0.35.1)
    Requirement already satisfied: python-dateutil>=2.5.3 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (2.9.0.post0)
    Requirement already satisfied: tinysegmenter==0.3 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from newspaper3k) (0.3)
    Requirement already satisfied: soupsieve>1.2 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from beautifulsoup4>=4.4.1->newspaper3k) (2.6)
    Requirement already satisfied: six in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from feedfinder2>=0.0.4->newspaper3k) (1.16.0)
    Requirement already satisfied: sgmllib3k in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from feedparser>=5.2.1->newspaper3k) (1.0.0)
    Requirement already satisfied: click in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from nltk>=3.2.1->newspaper3k) (8.1.7)
    Requirement already satisfied: joblib in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from nltk>=3.2.1->newspaper3k) (1.4.2)
    Requirement already satisfied: regex>=2021.8.3 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from nltk>=3.2.1->newspaper3k) (2024.7.24)
    Requirement already satisfied: tqdm in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from nltk>=3.2.1->newspaper3k) (4.66.5)
    Requirement already satisfied: charset-normalizer<4,>=2 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from requests>=2.10.0->newspaper3k) (3.3.2)
    Requirement already satisfied: idna<4,>=2.5 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from requests>=2.10.0->newspaper3k) (3.8)
    Requirement already satisfied: urllib3<3,>=1.21.1 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from requests>=2.10.0->newspaper3k) (2.2.2)
    Requirement already satisfied: certifi>=2017.4.17 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from requests>=2.10.0->newspaper3k) (2024.8.30)
    Requirement already satisfied: requests-file>=1.4 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from tldextract>=2.0.1->newspaper3k) (2.1.0)
    Requirement already satisfied: filelock>=3.0.8 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from tldextract>=2.0.1->newspaper3k) (3.16.0)



```python
!pip install newspaper
```

    ^C
    Traceback (most recent call last):
      File "/home/darsh22/nighthawk/darsh_2025/venv/bin/pip", line 8, in <module>
        sys.exit(main())
                 ^^^^^^
      File "/home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/pip/_internal/cli/main.py", line 77, in main
        command = create_command(cmd_name, isolated=("--isolated" in cmd_args))
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
      File "/home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/pip/_internal/commands/__init__.py", line 114, in create_command
        module = importlib.import_module(module_path)
                 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
      File "/usr/lib/python3.12/importlib/__init__.py", line 90, in import_module
        return _bootstrap._gcd_import(name[level:], package, level)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
      File "<frozen importlib._bootstrap>", line 1387, in _gcd_import
      File "<frozen importlib._bootstrap>", line 1360, in _find_and_load
      File "<frozen importlib._bootstrap>", line 1331, in _find_and_load_unlocked
      File "<frozen importlib._bootstrap>", line 935, in _load_unlocked
      File "<frozen importlib._bootstrap_external>", line 995, in exec_module
      File "<frozen importlib._bootstrap>", line 488, in _call_with_frames_removed
      File "/home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/pip/_internal/commands/install.py", line 15, in <module>
        from pip._internal.cli.req_command import (
      File "/home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/pip/_internal/cli/req_command.py", line 21, in <module>
        from pip._internal.index.package_finder import PackageFinder
      File "/home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/pip/_internal/index/package_finder.py", line 30, in <module>
        from pip._internal.req import InstallRequirement
      File "/home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/pip/_internal/req/__init__.py", line 8, in <module>
        from .req_install import InstallRequirement
      File "/home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/pip/_internal/req/req_install.py", line 40, in <module>
        from pip._internal.operations.install.wheel import install_wheel
      File "/home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages/pip/_internal/operations/install/wheel.py", line 242, in <module>
        old_csv_rows: List[List[str]],
                      ~~~~^^^^^^^^^^^
      File "/usr/lib/python3.12/typing.py", line 395, in inner
        return _caches[func](*args, **kwds)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    KeyboardInterrupt



```python
!pip install emoji
```

    Requirement already satisfied: emoji in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (2.12.1)
    Requirement already satisfied: typing-extensions>=4.7.0 in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from emoji) (4.12.2)



```python
!pip install newspaper
```

    Collecting newspaper
      Using cached newspaper-0.1.0.7.tar.gz (176 kB)
      Installing build dependencies ... [?25ldone
    [?25h  Getting requirements to build wheel ... [?25lerror
      [1;31merror[0m: [1msubprocess-exited-with-error[0m
      
      [31m×[0m [32mGetting requirements to build wheel[0m did not run successfully.
      [31m│[0m exit code: [1;36m1[0m
      [31m╰─>[0m [31m[1 lines of output][0m
      [31m   [0m [31;1mWARNING! You are attempting to install newspaper's python2 repository on python3. PLEASE RUN `$ pip3 install newspaper3k` for python3 or `$ pip install newspaper` for python2[0m
      [31m   [0m [31m[end of output][0m
      
      [1;35mnote[0m: This error originates from a subprocess, and is likely not a problem with pip.
    [?25h[1;31merror[0m: [1msubprocess-exited-with-error[0m
    
    [31m×[0m [32mGetting requirements to build wheel[0m did not run successfully.
    [31m│[0m exit code: [1;36m1[0m
    [31m╰─>[0m See above for output.
    
    [1;35mnote[0m: This error originates from a subprocess, and is likely not a problem with pip.



```python
pip install lxml lxml_html_clean
```

    Requirement already satisfied: lxml in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (5.3.0)
    Requirement already satisfied: lxml_html_clean in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (0.2.2)
    Note: you may need to restart the kernel to use updated packages.



```python
!pip install lxml[html_clean]
```

    Requirement already satisfied: lxml[html_clean] in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (5.3.0)
    Requirement already satisfied: lxml-html-clean in /home/darsh22/nighthawk/darsh_2025/venv/lib/python3.12/site-packages (from lxml[html_clean]) (0.2.2)



```python
import newspaper
from newspaper import Article
import emoji

url = 'https://www.washingtonpost.com/weather/2024/09/08/california-line-fire-evacuations-san-bernardino/?itid=hp-top-table-main_p001_f006'

article = Article(url)
article.download()
article.parse()
def add_emojis(text):
    emoji_map = {
        'happy': '😊',
        'love': '❤️',
        'money': '💰',
        'fire': '🔥',
        'good': '👍',
        'bad': '👎',
        'south': '🔽'
    }
    
    for word, emj in emoji_map.items():
        text = text.replace(word, emj)
    
    return text

article_with_emojis = add_emojis(article.text)
print(article_with_emojis)
```

    Firefighters are battling an eruption of wild🔥s in the western United States this weekend, with flames ravaging thousands of acres and triggering evacuation orders across California, Oregon and Nevada. Line Fire The quick-moving Line Fire in Southern California exploded over the weekend, consuming more than 20,500 acres as of late Sunday and forcing evacuations amid a searing heat wave in the region. It was zero percent contained as of just after 9 p.m. Sunday, authorities said.
    
    The blaze in San Bernardino County, which ignited late last week, quadrupled in size as the weekend began, scorching thousands of acres on Saturday alone. The flames raced up steep terrain, chewing through thick vegetation as they approached Running Springs, a mountain community of about 5,000 people that lies between the populated resort areas of Lake Arrowhead and Big Bear Lake. The community has been ordered to evacuate, while Lake Arrowhead and areas to its west are under an evacuation warning. By Sunday evening, Cal Fire estimated that the blaze threatened more than 36,000 structures, including family homes and businesses.
    
    The San Bernardino County 🔥 quadrupled in size over the weekend, and Gov. Gavin Newsom (D) has declared a state of emergency in the county. (Video: Menifee Battalion Chief via Storyful)
    
    Evacuation orders are also in effect on the 🔽 side of the 🔥, while structures could be affected in the city of Highland, which lies at the base of the mountains in San Bernardino County. Three 🔥fighters had been injured battling the blaze as of Sunday afternoon, according to a Cal Fire incident update. “Hot and dry conditions mixed with thunderstorms are expected to challenge 🔥fighters for the next few days,” the update stated.
    
    Advertisement
    
    Gov. Gavin Newsom (D) proclaimed a state of emergency in the county to secure federal assistance to respond to the 🔥, which is threatening homes as well as critical infrastructure.
    
    The 🔥 has “room to grow now in essentially three directions and there are population centers and pretty dense, dry vegetation in between those population centers,” UCLA climate scientist Daniel Swain said in a Saturday briefing.
    
    The 🔥 initially sparked Thursday and had burned about 3,800 acres by Saturday morning, before ballooning thousands of acres through the afternoon. The blaze was so intense that it also formed a towering pyrocumulonimbus cloud — a 🔥-generated thunderstorm — that was sending out its own lightning, erratic winds and brief rain.
    
    The Line Fire is spreading amid a scorching heat wave in Southern California that has rivaled one seen in September 2020, with temperatures approaching or tying all-time records, exceeding 105 and even 110 degrees in many locations.
    
    Advertisement
    
    Vegetation in the area is “critically dry,” according to the San Bernardino National Forest.
    
    “The San Bernardino front country … has everything you need for a 🔥 to get big,” retired Cal Fire assistant chief Tim Chavez said in an interview posted online by the Lookout, a wild🔥 reporting website.
    
    Along with this week’s heat, Chavez said, that includes heavy fuels that in most places haven’t burned since the 1990s — and “steep, steep terrain leading up to the mountain communities.”
    
    “Fuels that are stressed like that — they tend to surprise you,” he said.
    
    Firefighters battled fast-spreading wild🔥s ravaging thousands of acres across California and Nevada this weekend, forcing many residents to evacuate. (Video: Naomi Schanen, Anna Liss-Roy/The Washington Post)
    
    Temperatures at the base of the 🔥 have been running about 105-110 degrees each day this weekend, Alex Tardy, a meteorologist with the National Weather Service in San Diego, said in an email.
    
    He compared the blaze to the El Dorado Fire, which sparked during the September 2020 heat wave, burning almost 23,000 acres in San Bernardino and Riverside counties.
    
    Advertisement
    
    “These 🔥s are occurring in light winds, but this one is a little more complicated because it had thunderstorms over it yesterday and likely today as well,” he said.
    
    Stormy skies cloud parts of the region, as monsoon thunderstorms in the area Saturday also helped to intensify the 🔥.
    
    “Unfortunately, the weather conditions over the next few days are not going to be favorable,” Swain said in the Saturday briefing. “It’s going to be very hot and relatively unstable over the next few days with some increasing winds next week.
    
    Cooler weather is expected to move in by midweek, but that transition could come with strong winds.
    
    Boyles Fire
    
    California 🔥fighters are also battling to contain blazes around Los Angeles County, San Diego County and the city of Clearlake, which is about 100 miles northwest of Sacramento.
    
    Advertisement
    
    The Boyles Fire in Clearlake, in Lake County, has burned through about 76 acres and was about 10 percent contained as of Sunday evening. Authorities issued evacuation orders for two parts of the town, displacing at least 4,000 of its approximately 17,000 residents.
    
    According to Cal Fire, which posted a Sunday night update from the Lake County Fire Protection District, the blaze has “impacted” about 30 structures, although it is too soon to assess the damage. It has also destroyed more than 40 vehicles, the agency said.
    
    Bridge and Roblar Fires
    
    The Bridge Fire has ravaged at least 800 acres around the Angeles National Forest northeast of Los Angeles and Pasadena. In San Diego County, the Roblar Fire northeast of Camp Pendleton burned through at least 950 acres and remained only 20 percent contained as of Sunday night.
    
    Firefighting aircraft flew over the Bridge Fire on Sept. 8. The blaze has burned more than 800 acres northeast of Los Angeles and Pasadena, Calif. (Video: Angeles National Forest via Storyful)
    
    Fires in Nevada and Oregon
    
    Wild🔥s also raged Sunday in other parts of the western United States, including Nevada and Oregon.
    
    Advertisement
    
    In Oregon, multiple blazes in Deschutes County and northern Lake County have torn through thousands of acres of land and prompted evacuation notices. The Firestone Fire, 🔽east of Paulina Lake and within roughly an hour’s drive of the city of Bend, burned through at least 6,500 acres as of early Sunday evening. Meanwhile, the Flat Top Fire in the Deschutes National Forest has burned through at least 13,600 acres.
    
    In Nevada, strong, dry winds helped propel the Davis Fire 🔽 of Reno to roughly 6,500 acres, sparking a state of emergency declaration. Roughly 20,000 people have been evacuated ahead of the flames, according to the declaration from Nevada Gov. Joe Lombardo (R).
    
    The 🔥 destroyed at least 12 structures and continued to spread quickly Sunday, forcing new evacuations.
    
    The Western 🔥 season has roared back to life this past week as hot, dry conditions have returned. There are at least 70 large 🔥s burning out West, including 21 in Oregon, 19 in Idaho and 13 in Montana. A mix of wind and dry thunderstorms forecast for the coming days could exacerbate the situation and further strain 🔥fighting resources.
    
    Excessive heat in California is fueling the 🔥s
    
    The heat that has helped fuel the 🔥s has been extraordinary, especially in Southern California.
    
    Advertisement
    
    Downtown Los Angeles has observed its hottest weather of the year with highs near and above the century mark on four straight days. On Friday, it soared to a calendar-day record of 112, which tied for its all-time second-hottest day. On Sunday, it reached 104, another calendar-day record and one of many in the region.
    
    Other notable high temperatures include:
    
    Palm Springs: 121 degrees Friday.
    
    Death Valley: 119 on Thursday and Friday; it has reached at least 116 every day this month.
    
    Burbank: 114 on Thursday and Friday, tying the all-time high.
    
    Long Beach: 109 on Friday, a calendar-day record and fifth hottest of all time. It has reached at least 100 on four straight days , tied for most on record. A fifth is possible Monday.
    
    Widespread dangerous heat is forecast to persist in Southern California for one more day before starting to ease Tuesday. By Wednesday, highs will decrease into the 70s and 80s in most areas outside of the deserts because of a wind off the ocean.
    
    More dangerous 🔥 weather on Monday
    
    A red-flag warning for dangerous 🔥 weather runs until 11 p.m. Monday in the Santa Ynez Mountains and coastal areas in 🔽west Santa Barbara County because of the combination of heat, low humidity and strong winds. Gusts of 30 mph or higher remain possible, with erratic and gustier winds a threat near any large 🔥s.

