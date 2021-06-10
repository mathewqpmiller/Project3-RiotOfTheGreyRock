# Project3 in Machine Learning and visualizations: Honeybees and pesticides
# Completed by the group Riot Of The Grey Rock

Project status: completed with visions of future updates
Most models and many visualizations, summaries, and final presentation document have been completed.

## Introduction

The purpose of this project was to apply our newly developed visualization and machine learning skills to a dataset of interest.  The data set selected was regarding honey bees and honey production, pesticides, and the correlation between the two. Technology and packages required include Pandas, Python, Sklean, and Tableau to name a few. 

The end results are a variety of predicitve models of bee colony growth or decline along with visualizations of the initial data set.  The programs and packages selected to create these results were due to our pre-familiarity with them.

### Replicate the process:
To replicate this project, you will need to have the programs and packages as well as the environments activated that are within the Requirements.txt file.
* From the below website, download vHoneyNeonic_v03.csv.
DATA LINK: https://www.kaggle.com/kevinzmith/honey-with-neonic-pesticide?select=vHoneyNeonic_v03.csv
* Using Excel, create two additional fields: Colony Growth and Colony Outcome. (Note to future selves: figure out how to do this in Python for the purposes of skipping this step and excluding Excel as a required software). Colony growth is the rate of change per number of colonies based on state and year.  Growth outcome is a binary field based on colony growth.  (0 for growth loss or no growth, 1 for growth increase.) For an example, see the vHoneyNeonic_v03_with_growth.xlsx file included in this repo.
* Set up a new conda environment using reqirements.txt.  Then activate to start running the process.
* Clean the modified dataset using the DatasetCleanup file.  This will produce the working data set.
* Apply the logisticRegression, SVCModel, and randomForestClassifierModel, and neuralNetworkModel to produce machine learning results on the test and train variability of the Colony Outcome field.
* Run the Tableau workbook to re-produce initial data investigation and final report.

### Challenges:
* In raw data, all pesticides were in kilograms instead of pounds.  It was decided to leave as kilograms for the purposes of machine learning as this was consistent across the pesticides and removed a type conversion. However, in the graphical presentation, a conversion was applied to the pesticides to transform into pounds for the purposes of comparing honey prodution vs pesticide application.
* In the logisitic regression model, the first scenario reflected an error of a scalar requirement, but not with the remaining scenarios. The warning error was a bit misleading to researching what the solution was. Rabbit hole ensued. The resolution was to apply and increase max iterations to eliminate warnings and errors.
* A inclination to look into the affects of each individual pesticide proved challeging as there was only one pesticide that was applied outside of a combination of other pesticides. This was ImidaclopridLB (pesticide 2).  Therefore applying filters to create the different scenarios ended with no records for all but ImidaclopridLB.  Instead the scenarios could be created by elimintating pesticide fields that were not applicable to the specific scenario. This would be something to research in the future.

### Conclusion:
* Five scenarios were used in the four models: 
1. All fields included
2. Top five predictors in the random forest with grid search: ProductionValue, TotalProduction, ImidaclopridLB, Stocks, PricePerLB 
3. Just the individual pesticides: Clothianidin, Imidacloprid, Thiamethoxam, Acetamiprid, Thiaclolprid
4. Just the pesticides combined: CombinedNeonic
5. Exclude the pesticides: ColonyCount, TotalProduction, YieldPerColony, PricePerLB, ProductionValue, Stocks

* Outside of standard data cleaning and collaboration challenges, the anticipated results were that an increase in pesticide usage would contribute to colony collapse.  (e.g. correlation between pesticide application and decrease in colony growth.) Instead, no obvious correlation was found.  The neural network with scenarios two and five provided the best predictive results, though those results were exactly the same, which is suspecious.  Further review of the neural nework coding is in order.

* Given more time, there are updates and interests.  These include translating the Excel data cleanup in Python and simplifying some of the coding.  Additionally, time studies across the nation and each state might lead to better indicators of correlation between pesticide and colony decrease or increase.  Other datasets might be brough in such as weather or temperature patterns, wildflower or plant populations, and human development. These are things that would affect the bees atmosphere, food, and habitat.




## Below are the specifications of the assignment

#### Machine Learning Group Project

For this project we had to idendify a real world problem that needed to be solved. In order to do this we had to analyze a problem using Machine Learning, along with another Machine Learning library, and create some predictions based on our deep dive of the exhisting data. Once we came up with a solution to the problem we then had to create visualizations that explained our final analysis and that could be published on Tableau Public server. 

##### Task 1: Identify Real World Problem
For this section of the project, the teammembers met on Zoom and discuss a project proposal to do an analysis on. Each teammember presented topics to the group such as mushroom species, home loan predictions, Honeybee Colonization vs Pesticide use, AirBNB rentals and UBER user retention. After presenting each of our ideas to one another, we decided to do an analysis on Honeybee Colonization. We chose to do Honeybee Colonization vs Neonic Pesticide use because we thought topic was interesting and the dataset was fairly complete. Some of the things that we discussed analyzing and visualizing were. 
* Read Dataset into Jupyter Notebook
* Clean dataset: remove nulls, rename columns
* (ETL) Hawaii missing pesticide data
* Identify potential features that can be created by combining from raw datasets
* Identifing and run models that work with our dataset
* Compare models by success rate
* Assess modeled predictions with dummy data
* Do final visualizations in Tableau compared to predictive models

Neonic pesticide affects on HoneyBee colonies within the US



##### Task 2: Solve Problem with Machine Learning
* Solve the problem by making predictions
The predictions this group was interested in was based on pesticides vs Gowth Outcome. 
* Use Machine Learing
* Use Scikit-Learn and/or another Machine Learing library
* Incorporate two of the following: Python Pandas, Python Matplotlib, HTML/CSS/Bootstrap, JavaScript Plotly, JavaScript D3.js, JavaScript Leaflet, SQL Database, MongoDB Database, Google Cloud SQL, Amazon AWS or Tableau
The group decided on logistic regression, SVC, random forest, and neural network models applied to each of the 5 pesticides as well as the aggregrated pesticide.  To recreate this work, you will need to make sure the various programs and packages in the requirements.txt file are installed on your computer and in your environment.
* If building an app, deploy it to Heroku or another tool of choice.
The group decided against deploying an app and instead used Tableau to create a presentation

##### Task 3: Create Presentation
* The presentation had to clearly explain our problem, our deep dive analysis and our predicted results
* The presentation had to be 15 minutes or less
* Everyone had to participate in the presentation
* We had to create the presentation in Tablue and publish it to the Tableu Public with links to README.md and GitHub repo

##### Submission:
* Link to Google Doc with written analysis of results
* Links to any Google Colab notebooks if used
* Link to Tablue Public Story which explains the process in full
* Link to GitHub Repository where all of the files for project are located
* Collaboration on Jupyter Notebook for Python
* Thorough README.md with detailed explanation of the project steps 
* A link to a live deployed web app that describes the problem, explains process and uses model in real time



### References:
* Kevin Smith 2018, Honeybees and Neonic Pesticides, Kaggle, viewed 24 May 2021, <https://www.kaggle.com/kevinzmith/honey-with-neonic-pesticide?select=vHoneyNeonic_v03.csv>
* Census.gov, Geographies, 2018 FIPS Codes, viewed 25 May 2021, <https://www.census.gov/geographies/reference-files/2018/demo/popest/2018-fips.html>. 

#
#
<p align="center">
UNIVERSITY OF OREGON: Data Analytics Boot Camp - Repository for Group Project 3(Machine Learning Challenge)
</p>
<p align="center">
Lauren Toothaker, Julie Garvert and Mathew Miller © 2021. All Rights Reserved.
</p>
