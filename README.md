## How has representation in film evolved over time?

Our data story website can be found at https://oliviashii.github.io/ada-website/

### Abstract

As the world begins to become more aware of the oppression that minority groups face, representation in the film industry, both on and off screen, has become an increasingly pressing issue. We want to discover if the film industry has made substantial systemic changes to evolve along with society. Using the CMU Movie Summary Corpus dataset, Kaggle's Movie Datasets, and IMDB's Movie Datasets, we will compare the character metadata and crew data of older films to that of more recent films and see disparities in ethnicity and gender using a paired t-test. Further, we can analyze the movie summaries in the CMU datasets to compare how important minority characters to the storyline compared to their co-characters by applying coreference resolution to measure how often they are mentioned in the film plot. These analyses will determine if there have been significant changes in the film industry over time.

### Research Questions

- Has there been improvement in diversity regarding ethnicity and gender in the main cast? Crew?
- Are trends over time genre specific or general?
- Do movies delegate important roles to minority actors?
- Is there a correlation between movies that have a minority cast and the movie's budget? Box office performance?

### Proposed Additional Datasets

1. [Kaggle Movies Dataset](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset?select=ratings.csv)
This dataset has more information on budget and box office performance, which are valuable metrics to measure
performance of a movie. The current CMU Movies dataset lacks data on revenue and budget for each movie. We can use movies_metadata.csv in the Kaggle datasets, and get the 'revenue' and 'budget' columns to analyze. By combining this with our current dataset we will reduce the proportion of missing data.

2. [IMDB Datasets](https://datasets.imdbws.com/)
This dataset contains information on more recent titles. We will use this dataset to further supplement the lack of data on recent movies. In particular, we will use the name.basics and title.principals datasets to gather information on actors and actresses, and combine this with our dataset on actors' and actresses' ethnicities databse from the CMU corpus.



### Methods

#### Step 1. Data filtering and dataset construction

- Replace freebase ID's with their associated field. For example, in characters_metadata.csv, there are columns with character's name, and actor, but the movie column is an ID so we have to replace these to properly interpret the data.

- Find importance of each character by number of mentions in the movie's summary by using Spacy's coreference resolution libraries.

- Correctly map each Actor to a broader subgroup to see if they are a majority group or minority group, as well as a group in power with respect to ethnicity and gender. 

- Merge external datasets by using actor and movie fields as shared columns

#### Step 2. Exploring the change in diversity over time

- Using each movies' release date, crew, and casting information, we will determine whether or not there was a significant change in the number of minority cast and crew members and identify potential trends. By leveraging both the IMDB dataset and the CMU cast metadata, we will construct groups of minorities based on ethnicity and gender. We will then count the number of minority cast and crew members involved with each film and see how this changes over time. We can further break this analysis down by genre to see if specific genres have been more progressive.


#### Step 3. Exploring the type of representation within films

- Frequency of characters name in plot summary as indicator of importance
    - In order to determine whether or not minority cast members are playing significant roles in each film, we will perform an analysis of the plot summary to count the number of occurances of each character's name. We will use coreference resolution to attruibute pronouns to specific characters, and use the total number of occurances as a significance score for each character. Once we have each character's significance score for each movie, we will compare how significant the characters played by minority cast memebers are over all movies to look for changes and trends over time.

#### Step 4. Exploring the economic impact of diversity

- Correlation between box office performance, budget, and diversity of cast and crew
    - In this step, we will examine whether or not there exists a correlation between the number of minority cast and crew members, and the revenue generated by the movie. We will repeat the process to examine whether or not a correlation exists between the number of minority cast and crew members and the budget to make the movie. We could also use a t-test to determine whether or not there is a significant difference in the box office performance of movies with more or less than a number X of minority cast and crew members.

#### Step 5. Use visualization techniques to deliver findings of Steps 2,3, and 4

- Using data visualization techniques we can plot our findings to show: 
    - How diversity has changed over time
    - Proportion of representation
    - Show average importance of characters in different groups progress overall and per genre
    - Econmic impact of diverse cast and crew

Step 6: Package everything for the final notebook and to be Github ready, create final datastory website and text

### Proposed Timeline

- 18.11.2022 - P2 Milestone Due
- 25.11.2022 - Week 1
    Step 1
- 02.12.2022 - Week 2
    Step 2, 3
- 09.12.2022 - Week 3
    Step 4,5
- 16.12.2022 - Week 4
    Step 6
- 23.12.2022 - P3 Milestone Due

### Team Organization

- Andy: Change in diversity over time (Step 2), Exploring minority representation (Step 3), prepare datastory website, contribute to final datastory text
- Arvind: Character importance ranking changes overtime, freebase ID remapping, contribute to final datastory text
- Olivia: Change in diversity over time (Step 2), Exploring minority representation (Step 3), Visualizations (Step 5), contribute to final datastory text
- Owen: Change in diversity over time (Step 2), Exploring minority representation (Step 3), Economic Impact explorations (Step 5), contribute to final datastory text

