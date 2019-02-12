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
As a team we will break the data set into three segments:
- Train
- Test
- Validation

# End Goal
Before transaction is committed / approved, run data thorugh model automatically.  Put transactions onhold as being fradulent and flag for manual review.
