# Anomaly Detection
To identify potential fraudulent transactions before transaction execution and reduce financial loss due to criminal activity.

# Learning about Fraudulent Transactions
Historically, a fraud model was used in the financial services industry to automatically detect unauthorized charge card transactions, determine when a card has been used without the card owner's consent, maintain network's security, and ensure payment service integrity.<sup id="a1">[1](#f1)</sup>

As new payment services are introduced (e.g. <a href="https://pay.amazon.com/">Amazon Pay</a>), these new services will often access funds directly from a bank account, which means that this type financial service/product does not benefit from the fraud detection that a card network or issuer provided in the past.<sup id="a2">[2](#f2)</sup>

Introducing new fraud models provide a way to mitigate these different types threats against these new payment services and protect users and merchants of this service. Additionally, these new fraud models will play a pivotal role in the payment service providers’ profitability and sustainability.<sup id="a3">[3](#f3)</sup>

There are two high-level models that are associated with fraud: rules-based and algorithmic (machine-learning) models.<sup id="a4">[4](#f4)</sup>  While we will focus on the algorithmic model in our team project, it will be good to review/cover the differences between the two.

# Rules-Based Models
A rules-based model is a collection of rules used to identify fraudulent transactions. A single rule contains as a set of conditions that, when satisfied, label a transaction as fraudulent or potentially fraudulent.<sup id="a4">[4](#f4)</sup>

Some example rules are<sup id="a4">[4](#f4)</sup>:

- If a user receives payments for large amounts from multiple newly created accounts
- If a charge occurs at an infrequently visited gas station far from the card’s billing address
- If someone from the same IP address is creating multiple accounts and sending money with credit cards

Because rules-based models are just collections of conditions, they are easy to interpret. This extra transparency makes it simpler to diagnose and identify issues, e.g., why a model fails to identify a fraudulent transaction or mislabels a legitimate transaction as fraudulent. The interpretability also enables modelers to rapidly develop rules once a new threat is discovered.<sup id="a4">[4](#f4)</sup>

Rules-based models are much simpler than their algorithmic counterparts. Their simplicity provides many benefits in the development cycle. For one, modelers have an easier time developing and validating rules-based models. Engineers also benefit from an easier system to implement. Rules-based models are also much faster in operation, which can be an important factor when dealing with a large number of transactions in real time.<sup id="a4">[4](#f4)</sup>

# Algorithmic Models

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
[<b id="f1">1</b>] https://fin.plaid.com/articles/algorithmic-and-rules-based-fraud-models<br/>
[<b id="f2">2</b>] <i>ibid.</i><br/>
[<b id="f3">3</b>] <i>ibid.</i><br/>
[<b id="f4">4</b>] <i>ibid.</i><br/>


