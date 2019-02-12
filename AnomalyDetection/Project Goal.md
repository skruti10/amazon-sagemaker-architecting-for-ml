# Anomaly Detection
To identify potential fraudulent transactions before transaction execution and reduce financial loss due to criminal activity.

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
- Train - 70&#37; for training
- Test - 20&#37; for testing
- Validation - 10&#37;  for validation

Initially the team thought we should keep all the fields in the data set, as the data was being described to be ready "as-is".  We did conduct some exploratory analysis and attempted to find casual relationships.

After additional analysis, we determine that we should drop the fields <b>isFraud</b> and <b>isFlaggedFraud</b> as we are attempting to do an unsupervised training model.

# End Goal
Before transaction is committed / approved, automatically run data thorugh model.  Any transactions flagged as being fradulent would be automatically put on hold and flagged for manual review.
