# GroupProject
# Restaurant Data Web Scraping and Analysis

This project involves scraping data about restaurants from the website "trouvetonresto.be/bruxelles", building a machine learning model to analyze the data, and creating visualizations based on the results. The objective is to help restaurants owners to have an idea about what impacts their restaurant rating in Bruxelles. 

In this project, we planned to train a model to predict users’ rating of a business. The motivation includes that if we can predict how a user is going to rate a business, then we can recommend the business that the user is more likely to rate higher than the others.

## Instructions

To build and run this project, please follow these steps:

1. Clone the repository to your local machine.

2. Open the "ProjectWebscraping.ipynb" file. This is a jupyter file where we did the webscraping and retrieve all the data in a csv file. This csv file is in the repository and is called "DataRestaurants.csv". 

3. Run the first part of the code in order to be sure all the required libraries are installed. 

4. Run the web scraping script to collect the restaurant data from "trouvetonresto.be/restaurants/Bruxelles". The script will store the scraped data in a CSV file for further analysis. The script has been done so that one page at the time is retrieved, therefore you will need to run the entire script. 

5. Futhermore, we had to do a lot of data cleaning (This is explained in the Limitations part). That is why you will need to download the csv file in github named "DataRestaurants.csv".

6. Once you have the correct csv file, you can proceed to the machine learning model.

- Open the Jupyter Notebook `restaurant_analysis.ipynb`.
- Follow the instructions and run the code cells to preprocess the data, build the machine learning model, and analyze the results.

7. After running the notebook, you will find the generated visualizations in the output cells. These visualizations include bar charts, scatter plots, and heatmaps to provide insights into the restaurant data.

## Description

This project aims to gather information about restaurants from the "trouvetonresto.be/restaurants/Bruxelles" website and perform analysis using a machine learning model. The web scraping script collects data such as restaurant names, locations, ratings, average budgets and cuisine types. The collected data is gathered in a csv file and is then used to train a machine learning model that can predict the rating of a restaurant based on various features. 

The Jupyter Notebook `restaurant_analysis.ipynb` demonstrates the data preprocessing steps, feature engineering, model training, and evaluation. The notebook also includes visualizations of the data distribution, correlations, and predictive performance of the model.


## Limitations 

We had an issue with retrieving a certain type of data on the website. After a lot of research and analysis of the html structure of the website, we figured there was an anomality in the way the website put those additionnal variables. Therefore we had to limit our webscraping to those variables : Name, Location, cuisine type and rating. 
Futhermore, as usual in data webscraping, there was a lot of unavailable values in our retrieved data. In our case, this concerned only some ratings and some average budgets. We made the decision to add these information we were lacking for some restaurants from "tripadvisor.com" in order to have a complete and clean data. 

## Deployed Application

To access the deployed application and explore the visualizations, please visit the following link: [Restaurant Data Analysis](https://example.com)
