# CommanderGrams
### Bringing NLP to MTG! 
<sub>NLP = Natural Language Processing || MTG = Magic the Gathering</sub>
#### A look at trends to aid with Deck Building!
Commander is a format of Magic the Gathering that forces you to select a card (called your Commander) that you have access to throughout the game.  The goal of building your deck is to compliment or synergize with that card, however you can only use 1 of each that you select and the deck must be exactly 100 cards. In a 30 year old game, with 30,000-35,000 unique cards that contain over 200 keywords (essentially one or two words that have sentences or paragraphs of rules text associated with them), where do you start?
This repository contains 2 'apps' that come together to create a deck building app designed to help Commander players get started and better maintain their deck.  I am bringing some aspects of NLP into the my data pipeline in order to try to give players better insight into building with new Commmanders.

There are 3 repositories that make up the whole project.  They can be found here:
**THIS IS A PLACEHOLDER. WITH THIS API, ONCE YOU SEARCH THE REPO, IT LOCKS IN THE DESCRIPTION, AND I WANT TO UPDATE STUFF STILL!!!!!!**
<div>
  <p>
    <a href="https://github.com/robertblindt/CommanderGrams-Backend">
      <img src="https://github-readme-stats.vercel.app/api/pin/?username=robertblindt&repo=CommanderGrams-Backend&theme=dark" alt="GitHub Stats"/>
    </a>
    <a href="https://github.com/robertblindt/CommanderGrams-Frontend">
      <img src="https://github-readme-stats.vercel.app/api/pin/?username=robertblindt&repo=CommanderGrams-Frontend&theme=dark" alt="GitHub Stats"/>
    </a>
    <a href="https://github.com/robertblindt/CommanderGrams-Scraper">
      <img src="https://github-readme-stats.vercel.app/api/pin/?username=robertblindt&repo=CommanderGrams-Scraper&theme=dark" alt="GitHub Stats"/>
    </a>
  </p>
</div>

## Project Overview
This was a delve into creating a CRUD application, and working with a 3 stack project.
- Used Flask, SQLite (working to upgrade to PostgresSQL/ElephentSQL through Render), and React
    - Used Selenium to scrape a page for data to then clean and retrieve related data from an API.
    - Processed and stored data in order to build decks and analyze collections in a SQLite database
    - Used Sklearn, Spacy, and Regex to clean and analyze the meaningful data.
    - Used React to trigger scraping and data analysis, create and log users, create decks, and show card data and the results of analysis

## Lessons Learned
- Learned how to set up Docker containers and deploy apps
    - Due to incorporating scraping into my data collection, I had to set up a docker container to run my back end.
    - My initial plan was to get it deployed on Render, so I also learned some Linux in order to set it up
        - Once I realized Chrome (and other browsers) and the NLP small core were large enough to put me into the $25 a month tier on Render, I pivoted towards using Amazon EC2 (Still in progress).  

- Learned to trigger and pass around a variety of functions and data through my own API.
    - Due to my desire to explore data while building up my app, I created a variety of routes that would return data to the user rather than just retrieve data from databases and APIs

- Setting up users and tokens for private and public access of data
    - During the first push of the apps MVP the deck are set to only be viewed by the owner, but I left breadcrumbs in the code from when I was originally setting it up to hopefully make it very quick to add public viewing options.
        - Altering the decks page access to tokenless, and then using the token to allow for the add and remove buttons to be visible.


## Credits
I am scraping from www.EDHRec.com, and getting my card data from www.scryfall.com.  This project would not be possible without their scraping and aggregating of data!

While deciding how it might be possible to pull meaning out of cards for the purpose, Alex Lucchesi was nice enough to share his Nearest Neibour project with me and walk me through how he treaded his data.  Without that guide, this would not have been possible!  Thank you so much Alex! 
His repository is [Here!](https://github.com/lucchesia7/mtg_app.git)