# Anomaly Detection
To identify potential fraudulent transactions before transaction execution and reduce financial loss due to criminal activity.

# Learning about Fraudulent Transactions
Traditionally, fraud models in the financial services industry were developed to automatically detect unauthorized credit card transactions. Card issuers like Chase or Capital One use fraud models to determine when a card has been used without the owner's consent. Card networks like Visa or MasterCard use models to identify fraudulent card use in order to maintain their networks’ security and integrity, a key component of the service they provide for merchants.<sup id="a1">[1](#f1)</sup>

But the recent proliferation of payment services presents new types of fraud challenges. Many new services often access funds directly from a connected bank account, which means they do not benefit from the fraud protection a card network or issuer might provide. Additionally, payment services also face specific, unique types of fraud problems.<sup id="a2">[2](#f2)</sup>

Fraud models provide a way to mitigate these threats and protect users. Consequently, these models play an essential role in payment service providers’ profitability and sustainability. This post breaks down the factors that play into two high-level models: rules-based and algorithmic (or machine-learning) models.<sup id="a3">[3](#f3)</sup>

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

# Model Selection
We are going to work thorugh a unsupervised model using Random Cut Forest.  Once we complete the analysis of this model, we will determine an appropriate supervised model to compare and contrast the two models.

# End Goal
Before transaction is committed / approved, automatically run data thorugh model.  Any transactions flagged as being fradulent would be automatically put on hold and flagged for manual review.


# References
[<b id="f1">1</b>] https://fin.plaid.com/articles/algorithmic-and-rules-based-fraud-models
[<b id="f2">2</b>] <i>ibid.</i>
[<b id="f3">3</b>] <i>ibid.</>
