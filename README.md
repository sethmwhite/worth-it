# WorthIt

My app helps gamers on a budget decide which Steam games to buy this week by matching highly rated games to the genre, budget, and operating system they choose, as well as checking if a game is on sale.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/sethmwhite/worth-it/blob/main/Worth_It.ipynb)

> A course project for **MIST 4600: Computer Programming in Business** at the University of Georgia's Terry College of Business (Fall 2026).

## Problem
My users consist of PC/Laptop gamers that are looking for a new game but can't reach a confident decision. My users would use my app to account for their genre preferences, budget, their operating system, as well as whether or not they wish to include free games. This will allow my users to view high-rated games that match their liking.

## What it does
My app answers three sub-questions using the `steam_games.csv` file, which contains the 1000 most-reviewed games on steam:
1. **Sub-question 1:** Fit: which highly rated games match the genre and budget the gamer types in (`fit_games`)? The Rating means `pct_pos_total`, the percent of user reviews that were positive. Free games can be toggled on or off.
2. **Sub-question 2:** Compatibility: which of them run on the gamer’s operating system (Windows, Mac, Linux, etc.)(`games_for_os`)?
3. **Sub-question 3:** Deals: which of them are on sale today, and how close is it to its lowest price ever (`get_lowest_price`, using the CheapShark API)? The `GamePick` class stores each recommended game, then calculates a percent difference based on how far below the current price the highest discount was.
   
## Data
The [Steam Games Dataset](https://www.kaggle.com/datasets/artermiloff/steam-games-dataset) on Kaggle, collected in March 2025. The dataset is shared under the MIT License by its creator, artermiloff. This repo uses `steam_games.csv`, a smaller file made for the course: the 1,000 games with the most reviews.

## Built with
- Python and pandas, in Google Colab
- My Outside Tool: CheapShark web API 

## How to run it
1. Open `Worth_It.ipynb` from this repository on Google Colab, or click "Open in Colab".
2. Put `steam_games.csv` in your Google Drive, in the same folder as the Colab notebook.
3. Choose **Runtime → Run all**, and allow access to Google Drive when Colab asks you.
   * If you'd like to test different genres, budgets, etc., use the top of final cell to input different info.

## Example output
* Final Cell: A user would like to find an Action game on Steam for their Mac laptop, not including games that are free, with their budget's limit being thirty dollars.
* Once this information is put into the cell, the output lists the number of matching games that fit based on genre and budget. Below that, theres another number listing the total games that run on the user's OS, Mac. Then, a list of the top ten matching games fill the rest of the output, displaying the name, rating, current price, highest discount percentage, and the lowest recorded price via CheapShark.

<img width="1754" height="500" alt="image" src="https://github.com/user-attachments/assets/c7399757-0672-413b-bf50-2eff51ea03de" />



## AI Use Disclosure
* Tools Used: Claude
* What I Asked: I asked Claude to assist me whenever I ran into any roadblocks while creating the code for each of my cells, like whenever I ended up with errors in my code I wasn't able to figure out myself.
* What I Changed: Renamed variables, added the option to include or exclude free games, and ended up dropping a fourth sub-question regarding popularity, as the data from a column wasn't recording exactly what I had thought it was.
* What I Wrote Myself: Project Idea, Sub-Questions, genre/budget/OS inputs, tests and fixes.
* I understand each line of code written: Yes

## Author
Seth White - MIST 4600, Fall 2026
