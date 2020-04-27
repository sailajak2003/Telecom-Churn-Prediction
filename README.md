
# Telcom Churn Prediction
 
## Churn

  This project predicts Churn i.e. the number of customers who are switching carriers to a different service.
  The idea is to figure out what factors determine this and see if any new offers to these customers would help the firm
  reduce Churn. Obviously the simplest solution would be offer the best possible deal for everyone but needless to say that 
  would not be profitable to the firm. So this solution should ideally highlight ways that would decrease churn without 
  substantial cost to the firm.

  With this in mind we proceed with some exploratory analysis.
 
#### 1. Data Exploration
 
We are using IBM samples data from Kaggle.

This data has  17000 rows and 23 columns. Other than "Churn" our target column
we look at the rest of the columns and did some exploratory analysis in the first part.
We used seaborn’s **countplot** to look at various columns impact on Churn
![Image description](https://github.com/sailajakarra/Telecom-Churn/blob/master/images/Unknown.png)
##### Total Churns per month is about 26.53%
![Image description](https://github.com/sailajakarra/Telecom-Churn/blob/master/images/Unknown%201.png)
##### This graph shows churn in senior citizens and they are less likely to churn.
![Image description](https://github.com/sailajakarra/Telecom-Churn/blob/master/images/Unknown%203.png)
##### This plot shows churn by contract type and as expected churn is very low for customers with one and two year contacts
![Image description](https://github.com/sailajakarra/Telecom-Churn/blob/master/images/Unknown%204.png)
##### This shows churn after binning tenure longer the tenure lesser the churn.

#### 2. Feature Engineering 
 
Here we look at the factors and do some factor engineering steps

Dummies: 'contract','paymentmethod','internetservice'

Binaries: 'gender''phoneservice','partner','dependents','paperlessbilling','churn', multiplelines


**One-Hot-Encoding**: We use one-hot-encoding on a few columns to convert Yes/No to 1/0.

**Binning**   : Tenure column needs to be re-engineered as bins

**Scaling**   : We use Scikit-learn Standard Scaler to scale the results on columns like monthly, total charges etc.

#### 3. Modelling
           
Finally, after the data is cleaned, we do a simple train/test split and start running various models.
Here are the results of the models
            
![alt text](https://github.com/sailajakarra/projects1-Telecom-Churn/blob/master/images/Screen%20Shot%202020-04-19%20at%209.12.20%20PM.png)
            
            
#### 4. Final Result
Based on the various models, the best performing model is **Random Forest** which has the best **F1 Score**.

