# Anomaly Detection
To prevent card fraud before it happens and reduce financial loss due to criminal activity.

# Datasets
The data source is retrieved from: https://www.kaggle.com/ntnu-testimon/paysim1<br/><br/>
The data fields in this data set are as follows:<br/>
- <b>stepMaps</b> - a unit of time in the real world. In this case 1 step is 1 hour of time
- <b>type</b> - CASH-IN, CASH-OUT, DEBIT, PAYMENT and TRANSFER
- <b>amount</b> - amount of the transaction in local currency
- <b>nameOrig</b> - customer who started the transaction
- <b>oldbalanceOrg</b> - initial balance before the transaction
- <b>newbalanceOrig</b> - customer's balance after the transaction
- <b>nameDest</b> - recipient ID of the transaction
- <b>oldbalanceDest</b> - initial recipient balance before the transaction
- <b>newbalanceDest</b> - recipient's balance after the transaction
- <b>isFraud</b> - identifies a fraudulent transaction (1) and non fraudulent (0)
- <b>isFlaggedFraud</b> - flags illegal attempts to transfer more than 200.000 in a single transaction

# Modeling Strategy
- At this point ignore that anything is CASH-IN. 
Break up events into types of crime. These are as follows. Each new day will be cross-referenced against a multi-class classification model that predicts each block for it's likelihood of having any of 7 types of criminal activity.
    - Kidnapping
    - Sexual assault 
    - Homocide
    - Motor vehicle theft 
    - Weapons violation
    - Battery
    - Theft
- Link with weather data
- Build a multi-class classifier to predict each type of crime
- Use sequential methods to model the add-on effect; because of what happened earlier in the year, this will happen. Most likely will need to model the sequence in a discrete window of time: One month? One quarter? One year? Will need to experiment here to find the right windo. 

Potentially use multi-class classification to rank blocks in the city based on their likelihood of having a type of crime in the coming day, given the weather forecast and all previously known criminal activity. 


Potentially use LSTM's to capture both the level of complexity and the sequential element. 

Open question: how do we standardize the sequence of both criminal events per block and weather events per block that lead up to the criminal event? Monthly? Yearly? For 2018 maybe just include the sequence of the last month. This means we need to chunk the data into month sequences that go into the LSTM's.

Is it actually better to think about this problem as forecasting? Where we're forecasting the level of crime? Unknown.

# End Goal
Heatmap that predicts crime multiple days in advance. Final system should be a website that queries the Chicago data portal and local weather sensors every day, retrains the model over night, and generates new predictions for the day's criminal activity.

Rather than getting side-tracked about the research goals, it might be more valuable to build the website first, and then load in new models over time as we ship them.
