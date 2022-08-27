# Disaster Response Pipeline Project

### Project Objective
This project objective is to analyze and classify messages during disaster using machine learning and designing a web app that will visualize the data. The data is extracted from [Figure Eight](https://appen.com/) to build a model for an API that classifies disaster messages. There is machine learning pipeline categorizes messages so that it can be sent to appropriate disaster relief agency. Application of the web app can be from an emergency worker, who can input a new message and get classification results in several categories.


### File Descriptions
app    

| - template    
| |- master.html # main page of web app    
| |- go.html # classification result page of web app    
|- run.py # Flask file that runs app    


data    

|- disaster_categories.csv # data to process    
|- disaster_messages.csv # data to process    
|- process_data.py # data cleaning pipeline    
|- InsertDatabaseName.db # database to save clean data to     


models   

|- train_classifier.py # machine learning pipeline     
|- classifier.pkl # saved model     


### Components
There are three components I completed for this project. 

#### 1. ETL Pipeline
The Python script, `process_data.py`, is the data cleaning pipeline. It performs the follow tasks:

 - Loads and categorize the data
 - Merges the message and category datasets
 - Cleans the combined dataset
 - Stores the dataset in a SQLite database
 
Jupyter notebook `ETL Pipeline Preparation` was used to do EDA to prepare the `process_data.py` script.
 
#### 2. ML Pipeline
The Python script, `train_classifier.py`, is the machine learning pipeline. It performs the following tasks:

 - Loads data from the SQLite database
 - Splits the dataset into training and test sets
 - Builds a text processing and machine learning pipeline
 - Trains and tunes a model using GridSearchCV
 - Outputs results on the test set
 - Exports the final model as a pickle file
 
The jupyter notebook `ML Pipeline Preparation` was used to do EDA to prepare the`train_classifier.py` script.

#### 3. Flask Web App
The project includes a web app where an emergency worker can input a new message and get classification results in several categories. The web app will also display visualizations of the data.


### Instructions of How to Interact With Project:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python Data/process_data.py Data/disaster_messages.csv Data/disaster_categories.csv Data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/
