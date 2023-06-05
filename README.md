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

6. Once you have the correct csv file, you can proceed to the machine learning models (there are a linear one and a decision tree).

- Open the Jupyter Notebook `linearmodèle (1).ipynb` and 'decisiontreemodel (1).ipynb'.
- Follow the instructions and run the code cells to preprocess the data, build the machine learning model, and analyze the results.

7. After running the notebook, you will find the generated visualizations in the output cells. These visualizations include bar charts, scatter plots, and heatmaps to provide insights into the restaurant data.

## Description

This project aims to gather information about restaurants from the "trouvetonresto.be/restaurants/Bruxelles" website and perform analysis using a machine learning model. The web scraping script collects data such as restaurant names, locations, ratings, average budgets, maximum capacity and cuisine types. The collected data is gathered in a csv file and is then used to train a machine learning model that can predict the rating of a restaurant based on various features. 

The Jupyter Notebook `restaurant_analysis.ipynb` demonstrates the data preprocessing steps, feature engineering, model training, and evaluation. The notebook also includes visualizations of the data distribution, correlations, and predictive performance of the model.


## Progress and Limitations

We had an issue with retrieving a certain type of data on the website. After a lot of research and analysis of the html structure of the website, we figured there was an anomality in the way the website put those additionnal variables. Therefore we had to limit our webscraping to those variables : Name, Location, cuisine type and rating (and forget about maximum capacity). 

Futhermore, as usual in data webscraping, there was a lot of unavailable values in our retrieved data. In our case, this concerned only some ratings and some average budgets. We made the decision to add these information we were lacking for some restaurants from "tripadvisor.com" in order to have a complete and clean data. The problem was that the rating were Non Avaible for a big part of the restaurants as well as the average budget. After getting a part of the lacking data from tripadvisor (this website isn't any more complete but help), we could attack the modeling part. 

Firstly we had to clean all the non avaible and empty data. Then, prepare the train and test data. We had a problem with the numerical data that were considered as an object and not float64 data. We tried to fix it and right after standardize (0 mean and unit variance) the numerical value and perform one-hot encoding on the 'Type' and 'Address' columns. We decided to go for a linear model and decision tree model (does not required linearity assumptions).


## Results

This is the tricky part here. We succeded to make the models but the results are quite strange. we wanted to check the MSE, the MAE, the R-Squared and the adjusted R-Squared. The MSE value is 0.4464912499771423, indicating that, on average, the squared difference between the predicted and actual values is relatively low (wich is pretty good) but the mae is higher (0.5000177500168457). 
Depending on the specific dataset and the distribution of errors, there can be situations where the squared errors in MSE are relatively smaller compared to the absolute errors in MAE. Plus,the R2 value is -0.05459258622687391, indicating that the model explains a small proportion of the variance and performs poorly in capturing the relationships between the features and the target. 
That just indicates that the model fails to capture efficienly the relationships between the data. 

We thought about what could inhance our metrics and come to a solution. We discussed the linearity of the model and decided to test with decision trees model to go over this assumptions but the results got worse. 

We came with hypothesis about the results. The subjectivity of the rating is very difficult to interpret since that depends on some people value and personnal experience. Plus, we did not have the number of votes, the results could be totally biased by the lack of votes (one perso with one bad experience or good).
We tried to compare with other similar projects with larger datasets (they just provide MSE). They did it with Baseline (1.40), Linear Regression(0.792), Random Forest Regression (0.6398) and Latent Factor Model (1.26). You could find it here (Yu, Mengqi, Meng Xue, and Wenjia Ouyang. ‘Restaurants Review Star Prediction for Yelp Dataset’, n.d.). Globally tehy got worst predictive power than us, tha is not a lot but confort us a bit with the lack of consistent of a model with restaurant's ratings.

