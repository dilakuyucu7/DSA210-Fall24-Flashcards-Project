# DSA210-Fall24-Flashcards-Project
## Description  
My term project for Sabanci University Fall 2024-2025 DSA210 Introduction to Data Science course. In this project, I analyze my language learning habits through my Flashcards World mobile app data.  

## Table of Contents
[Motivation](#motivation)  

[Dataset](#dataset)  

[Project Plan](#project-plan)




## Motivation
I have been interested in languages and language learning for as long as I can remember, and I have used various methods to enhance my language learning process. The most recent of them that I stuck with is the flashcard method, specifically the Flashcards World mobile app. The app has features such as premade sets as well as handmade sets, multiple review modes, progress reports etc.  

The languages I study are Korean, German and predominantly, Italian. The sudden uptick in Italian is due to me going on an Erasmus+ study program this upcoming spring in Bologna University, as I don't want to be completely lost in a country I'll spend 6 months in. Since I only started learning Italian this year, and did my learning mostly through Flashcards app, I'm hoping this project will give me a solid understanding of my current level. For Korean and German, I've already been studying them way before I downloaded this app, so I have minimal data on them. Nonetheless, I included them for the sake of completeness.                                    My Italian studies started on 18.03.2024. 
## Dataset
I have 2 types of main datasets in mind. The first one is my "Flashcard Data". I can pull this one from the Flashcards World app directly as a CSV file from every set. The CSV file contains the target word in my target language and its translation into (mostly) English. While processing this data, I'll assign an ID number to each word, which will help with tracking. The target language and the part of speech it belongs to (noun, adjective etc.) will also be added.  

The second dataset is "Progress Data". This data contains every review session I had, their dates and timestamps, the type of review (review mode), the words in the session, my correct/incorrect answers etc. The challenge is, the creator of the app said that this progress data cannot be exported, so I have to come up with a workaround.  

Additionally, I have my exam dates and other important deadlines in my calendar from November 2023, which I'm planning to use in this project.

## Project Plan
I more or less explained my plan with the Flashcard Data in the above section. This data will be used as my 'base', and the ID numbers are the keys that will help me keep this project organized.  

The Progress Data will be transformed into a form that assigns each review session a unique ID. The session ID will be based on the session date, timestamp and review mode. The word ID's will be matched to session ID's if the word was reviewed in that session, along with my correct and incorrect guesses for that word in that session. The challenge is with exporting this progress data, so I thought of using Appium to scrape it. If that fails, then I will have to manually log them as a last resort.  

The metrics I want to analyze are mainly my review frequency, accuracy, session trends, review mode success, word performance and other related input relations. I want to use heatmaps, pie charts, line charts and several other visualization techniques to spot trends and measure my performance in vocabulary. Additionally, using my calendar, the relationship between exam dates, important events etc. and my Flashcards World app usage will be added to the final results.



