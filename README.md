# DSA210-Fall24-Flashcards-Project
## Description  
Please head over to this presentation for detailed analysis after reading this README.

My term project for Sabanci University Fall 2024-2025 DSA210 Introduction to Data Science course. In this project, I analyze my language learning habits through my Flashcards World mobile app data.  

## Table of Contents
- [Motivation](#motivation)  

- [Tools](#tools)
  
- [Dataset and Data Processing](#dataset-and-data-processing)

- [Exploratory Data Analysis](#exploratory-data-analysis)

- [Data Visualizations](#data-visualizations)

- [Findings](#findings)
  
- [Limitations](#limitations)
  
- [Future Work](#future-work)




## Motivation
I have been interested in languages for as long as I can remember, and I have used various methods to improve my language skills. The most recent of them that I stuck with is the flashcards method, specifically the Flashcards World mobile app. The app has features such as handmade sets, multiple review modes, progress reports etc.  

The languages I study are Korean, German and predominantly, Italian. The sudden uptick in Italian is due to me going on an Erasmus+ study program this upcoming spring in Bologna University, and I used the app mostly for Italian. For Korean and German, I'd already been studying them before I downloaded this app, so there is minimal data on them. Nonetheless, I included them for the sake of completeness.  

## Tools
- **Appium** (for automating data extraction from the Flashcards World app)
- **Appium Inspector** (for identifying UI elements during automation)
- **Stanza** (for natural language processing)  
- **Python** (for data analysis and visualization)
- **Pandas** (data manipulation)
- **Matplotlib & Seaborn** (visualizations)
- **Scipy** (statistical analysis)
- **Jupyter Notebook** (for interactive analysis)

## Dataset and Data Processing
There are 2 important datasets. The first one is my "flashcard data". I pulled this one from the Flashcards World app directly as a CSV file from every set, which the app offers. The CSV file contains the target word in my target language and its translation into English.

The second dataset is "progress data". As this data was unexportable, I automated an Appium script to pull it from the mobile app, which is given above in "appium_mobile_app_scraping.ipynb". I first logged them as a text file, and then cleaned them to obtain a complete CSV file. It contains the target word, the date that card was added, the number of times it was studied, and my correct and incorrect answers. 

To add the Parts of Speech (POS) tagging, I used stanza on the raw CSV files and merged them with my Progress Data to create a complete dataset. The parts of speech tags include NOUN, VERB, ADJ, ADV etc. The code is given above in "pos_tagging.ipynb". 

## Exploratory Data Analysis  

During the exploratory data analysis phase, I examined patterns and relationships within the flashcard datasets for Korean, German, and Italian. Key steps included:

- **Data Cleaning:** Handled missing values and ensured data consistency across datasets.
- **Descriptive Statistics:** Calculated summary statistics for study frequency, accuracy, and POS distribution.
- **Visualizations:** Generated bar charts, histograms, and scatter plots to identify trends such as the correlation between the number of times studied and accuracy.
- **POS Tagging Analysis:** Explored how different parts of speech affect retention and correctness in language learning.
- **Language Comparisons:** Compared accuracy and study frequency across the three languages.

This analysis helped me identify important trends and patterns, guiding the next stages of hypothesis testing and findings.

## Data Visualizations

To better understand the patterns in the flashcard datasets, I created a series of visualizations to summarize key insights. The tools used for visualization were:

- **Matplotlib & Seaborn:** For static bar charts, histograms, and scatter plots.
- **squarify:** For treemaps.
- **Visuals Created:**
   - Bar charts to compare study frequency across languages.
   - Histograms for correct vs. incorrect answers, as well as the card addition date comparisons.
   - Line graphs showing learning progress over time.
   - POS distribution treemaps across different languages.
   - Heatmaps to display correlation relations betwen number of times the word was reviewed and the correct vs incorrect answers.
   - Word clouds to indicate most correctly vs incorrectly answered words in each language.


## Findings
Key insights:
- Consistent review leads to higher accuracy.
- POS distribution affects study patterns across languages.


## Limitations
There were several challenges I faced along the way.
- Mobile app data extraction: As the creator of the app did not supply progress data extraction, I had to automate Appium scripts to do it and due to my unfamiliarity with this setup, there might have been some errors with exporting the data. There were also more detailed progress reports on the app but since their UI was much more complex, I didn't have the expertise to extract and use them in the project.
- POS tagging: Due to stanza only perceiving the first word of the target word, there were some errors with POS tagging, which I had to fix manually. For example, for a German noun, it registered it as a "determiner" due to the article of the noun.
- Korean font: Some modules are not compatible with the Korean alphabet, so there were some adjustments needed to the codes. For example I could not generate a word cloud for lowest and highest accuracy rated Korean words beacuse it refused to process the Korean characters. You can see the example on "EDA_on_accuracy.ipynb".
- No external validation of learning effectiveness: The results of my flashcard analysis were not compared or validated against other independent sources to confirm if the observed trends actually reflect real learning progress. The analysis relies only on in-app performance, which is not enough for a full analysis of language learning habits.

## Future Work
- Expand the dataset for more languages in the future, or expand my datasets for the existing languages, German and Korean, especially.
- Create a website to track my full language learning journey.
- Automate and further develop Appium scripts to tackle the more complex progress data UI.




