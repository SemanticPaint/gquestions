# ❓❔👾 Gquestions CLI Usage ❔❓

 ![pybadge] (https://img.shields.io/badge/python-%3E%3D3.7-important.svg)  ![badge](https://img.shields.io/badge/license-GPLv3-brightgreen.svg)

NOTE:
More details about how to use at the bottom of the file...

Also note:
Likely need to substitute "python3" instead of "python" wherever "python" is used.

[![asciicast](https://asciinema.org/a/4wrOzHnxQVcTImuofzdMxB35L.svg)](https://asciinema.org/a/4wrOzHnxQVcTImuofzdMxB35L)

## ⚠ Disclaimer
> This software is not authorized by Google and doesn't follow Google's
> robots.txt. Scraping without Google explicit written permission is a violation of thei
> terms and conditions on scraping and can potentially cause a lawsuit

## Install dependencies
```
pip install -r requirements.txt
```

## 🔍 Usage:

```
python gquestions.py query <keyword> (en|es) [depth <depth>] [--csv] [--headless]
```

Print help message.

```
gquestions.py (-h | --help)
```

## 💡 Examples:
Search "flights" in English and export in html

```
python gquestions.py query "flights" en
```

Search headlessly "flights" in English and export in html
```
python gquestions.py query "flights" en --headless   

```

Search "vuelos" in Spanish and export in html and csv
```
python gquestions.py query "vuelos" es --csv
```

Search "vuelos" in Spanish with a depth of 1 and export in html
```
python gquestions.py query "vuelos" es depth 1 
```

Advanced use: using operators with queries:

```
python gquestions.py query '"vpn" site:https://protonmail.com/blog' en --csv
```

## License
All assets and code are under the GPL v3 License unless specified otherwise.

## 👀 Help:
Got stuck? Check help!
```
python gquestions.py -h
```

![Gquestions_graph](https://i.gyazo.com/5f9677d13ba9845e0f38972e4d8c6ed3.png)


anitto | SEO Consultant
HOME
TECH
ABOUT
Scraping Python SEO
Scraping 'People also asked' on Google Search
How to use Python to get better insights on contents

Posted by Alessio Nittoli on 13-06-2019
ToC
Gquestions.py
How it is made
Python
Selenium
d3
How to use it
How to use data
Ideas for new content
Improve existing contents
Question answering


Lately I binge-watched an amazing series on Netflix, “Mad Men”.

From the first episode I noticed a wild cigarettes and alcohol consumption.

I ask Google the total number of cigarettes smoked and, besides the actual answer ( 974 cigs in 94 episodes for 7 seasons), I had an idea.

Don Draper

PAA box

“People also asked” is a widget in SERP introduced in 2015: it gives us hints about how search engine tries to help user to refine his search.

Crescita PAASource: MozCast

Long story short: for each click on a question, Google will show us the page that is more relevant for that question.



Depending on what question we’ve clicked, more questions are loaded at the bottom of PAA box.

Then I asked myself: could I gather interesting insights from the way Google shows me questions? This is why I’ve written this script in Python.

You can download here from Github.

⚠ DISCLAIMER: This software is not authorized by Google and doesn’t follow Google’s robots.txt. Scraping without Google explicit written permission is a violation of their terms and conditions on scraping and can potentially cause a lawsuit
This software is provided as is, for educational purposes, to show how a crawler can be made to recursively parse Google’s “People also asked”. Use at your own risk.
Gquestions.py
How it is made
Python
python logo

Python is a versatile programming language used in a lot of fields (from data analyisis to machine learning and web development). Due to its low learning curve it is strongly recommended to beginners and non-techie guys.

To make this script work we need Python >= 3.7 . This is because from this particular version it can “remember” order of entries in dictionaries .

You can download the latest version here.

Once downloaded you’ll need to verify if the package manager Pip is installed (it should in the latest versions).

Open a terminal and digit:

pip --version
If no errors appear it means we’re almost ready!

To make the script work correctly, move into the script folder and download all dependencies:

cd <PATH_REPO_FOLDER>
pip install -r requirements.txt
This is the folder structure:

.
├── csv
│   ├──<keyword1>_<date>.csv
│   └──<keyword2>_date.csv
├── html
│   ├── <keyword1>_<date>.html
│   └── <keyword2>_<date>.html
├── driver
│   └── yourchromedriver
├── templates
|  └── index.html
├── gquestions.py
└── requirements.txt
Selenium
selenium

Selenium is an automation browser library. It controls a browser through a driver: for this script we’ll using chromedriver. With Selenium we’re also able to interact with pages.

Here you can find the right driver version based on your Chrome version (visit chrome://settings/help your version).

http://chromedriver.chromium.org/downloads

Once downloaded the zip archive, unzip in the driver folder.

d3
d3

d3.js is a powerful JS library used for data visualization. For this dataviz I’ve used a tree graph or dendogram.

Base version can be found at this URL.

http://bl.ocks.org/d3noob/8375092

How to use it
asciicast

Gquestions.py opens a new browser instance and search a query, clicking on each answer and generating a tree graph with d3.

Results are stored in the folder html/.

Move into the folder containing gquestions.py and type on terminal:

python gquestions.py query <keyword> (en|es) [depth <depth>] [--csv] [--headless]
query: search a query. If no PAA box is found, the script exits automatically. This is a mandatory command.
en or es: search in English or Spanish. This is a mandatory command.
depth: Set the click depth. Default 0, max 1. Optional.
--csv: Export all questions to a .csv file. Optional.
--headless: Start Chrome headlessly. Optional.
One-level-depth

I decided to limit the depth to only 2 levels because beyond the third level the graph becomes very messy.

Here you can see an example of 2 levels deep graph:

Two-level-depth

How to use data
These related questions give us a deeper insight than traditional keywords. Following there is a not exhaustive list of what you can use this data for.

Ideas for new content
Understanding what are the most common questions when users are searching for something is an amazing help if you are creating a new content or even a whole editorial plan.

We can also use the data to create FAQ pages.

Improve existing contents
We can use these questions to improve existing articles and make them more pertinent to the context.

It could also be a good idea to use them as paragraph headings or to improve title/meta description.

Question answering
Natural Language Processing (NLP) is a subfield of Machine Learning concerned with “understanding” texts and relations between topics expressed in textual contents.

Thanks to Deep Learning is also possible create models able to answer to questions in a content. All answers are extracted from the text.

Questions answering

One of the most famous dataset is SQuAD, released by Stanford University. It is a set of questions asked by some crowdworkers on Wikipedia articles. Every answer is a span in the text and, if not present, could make the question unanswerable .

Practically it is what Google does with contents of other sites when it shows the answer in PAA box.

To deepen this topic: Building a NLP Question Answering Model

Final words, thank you for your time reading this article and hope it helps! :)

Please leave a comment or drop me a line for any kind of feedback.

← PREVIOUS POST
FEATURED TAGS

js python scraping seo

Copyright © anitto | SEO Consultant 2019
🇺🇸 | 🇮🇹
