## IMDB Top 20 Titles Scraping and Score Adjustment

The goal of the developed code is to scrape the following data attributes for the top 20 titles of the IMDB top 250 page (https://www.imdb.com/chart/top). 

- Rating
- Number of ratings
- Number of Oscars
- Title of the movie

Once the data is scraped, the retrieved scores are adjusted based on the below logic. 

### Review Penalizer:

The number of reviews are arranged in descending order, to determine the title with the most reviews and use  it as a benchmark. Once the benchmark is determined, all the other titles are compared to the it. The ratings are then adjusted based on the followwing rule: Every 100k deviation from the maximum translates to a point deduction of 0.1. 

This approach allows to factor in the number of reviews as well as the rating, to provide a more accurate picture. 

### Oscar Calculator

In this project, oscars have a positive effect on a title's score.  
The scale of the rewards are listed below:

- 1 or 2 oscars → 0.3 point
- 3 or 5 oscars → 0.5 point
- 6 - 10 oscars → 1 point
- 10+ oscars → 1.5 point

### How to run the Notebook? 
In order to run the analysis, follow the steps below. 

- Please note, Jupyter is required to run the notebook
- Download the contents of the github repository to your local machine
- The required packages and versions are outlined in the requirements.txt
- The complete notebook can be executed in a linear fashion, without making any updates
- The notebook should yield two dtaframes, one for the initial scraping and a second one, which contains the adjusted scores, review penalties and oscar boosts
- The unit tests, at the bottom of the notebook, compare the data frames generated by the scraping and analysis functions to test data frames, which are stored in the data folder of this Github repository
- The unit tests serve as an indicator of data completeness
