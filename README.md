# Customer Satisfaction for Airline Travel

The aim of this project is to analyze trends in customer feedback of airport and airline experiences. 

First dataset context:
Customers have given their feedback in a variety of airline trips. The problem we are having has to do with customer satisfaction, there are many users that have been a long time with the airline and have shown dissatisfaction and likewise those users that are not loyal have also showed dissatisfaction with the service provided. It would be interesting to understand the role some variables play in the satisfaction result for these trips.
Second dataset context:
Airport customers have given feedback on a variety of features of the airport. For each of the features customers provide their level of satisfaction and also give an overall satisfaction. The problem we have is that there are many features in which customers show a dissatisfaction with the value provided by the airport; it would be interesting to understand which variables are the most important to the overall customer satisfaction.

## Description of the dataset

The first dataset has 129,880 records and has 23 variables that were measured per trip as detailed below:

<img width="834" alt="Screen Shot 2024-06-18 at 10 33 40 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/WhatsApp%20Image%202025-01-11%20at%201.13.34%20PM%20(1).jpeg">

The data was included in the source in 2020 and the information was anonymously given. The name for the airline used for this example is Invistico airlines. The rows represent the individual customer feedback, and the column names are the measures that capture the
customer related information as well as their experience of travelling with the company including how they have rated several airplane features. The columns also mention details about the flight that the customer has taken, as well as features of the particular airplane.
The second dataset has 3501 records and has 37 variables that were measured per customer as detailed below:

<img width="877" alt="Screen Shot 2024-06-18 at 10 34 23 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/WhatsApp%20Image%202025-01-11%20at%201.13.34%20PM.jpeg">

The data was first created for use in 2020. The information comes from customer surveys in Austin-Bergstrom airport. The surveys were conducted from 2015-2017 and are reported per quarters. The rows represent individual customer feedback and the columns detail the users overall satisfaction in many variables such as restaurants for example.

First dataset
Task a
As we can see in the image below, these are the number of missing values per column

<img width="455" alt="Screen Shot 2024-06-18 at 10 39 28 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/40662851-2dbf-44f3-9531-e52fa45652e0%20(1).jpg">

Given that the dataset is quite big and 393 ends up only being 0.3% of the total rows we have decided to drop the rows with this missing values.
Task b
The following image shows the count per class for the satisfaction variable

  <img width="229" alt="Screen Shot 2024-06-18 at 10 39 47 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/002d0086-b1f8-49dd-ba05-756285eeed5b.jpg">

Task c
 After validating the data types, they are all the right type of variable. We have classes for our categorical values and ordinal values for our ratings.
 
 <img width="617" alt="Screen Shot 2024-06-18 at 10 40 10 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/e02debf1-4568-47dc-ab6a-38a5ee4e4bc1.jpg">

Second dataset
Task a
Below we can see the number of missing values per column we have for the airport customer satisfaction dataset

<img width="381" alt="Screen Shot 2024-06-18 at 10 40 37 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/9aa95afa-267d-4ae7-b807-85db2307bf7a.jpg">

 Since we want to use the Overall satisfaction column as our classifier, we will drop the 172 rows which don’t have a value since they only make up a 5% of the data.
On the other hand we will impute the rest of the columns with the mode (given that as seen from the histograms, the data is very skewed) to make up for the missing values in each of the columns. We wish to keep them so as to not drop any more information that will come in handy for the classification task.

Task b
The following shows the count per label. It is important to note that users that gave a rating of 4 or 5 are classified as satisfied; all the other have been classified as not satisfied

<img width="176" alt="Screen Shot 2024-06-18 at 10 40 51 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/17a7c0c5-28c3-4ad0-baad-0ac3194ea488.jpg">

Task c
  After observing all the variables we see that they have the correct type needed for our classification

<img width="478" alt="Screen Shot 2024-06-18 at 10 41 05 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/91481cb9-8ffe-4f70-8ded-8317ab9acac4.jpg">

## Decision on keeping the datasets separate
We have decided to keep both the datasets separate as the questions answered from each data set can be answered by using the data in each separately. Both have different numbers of rows and columns, which will make it harder for the information to be merged. For data set one, we will predict whether the customer will take another flight with the airline or not as well as clustering the customer into different groups. For the second data set, we will mainly deal with the attributes that can have an impact on customer satisfaction using binary classification. For this reason, merging the datasets is not required and it is better to treat them separately.
Data Visualization
For both the data sets, we made a histogram and a regplot as that goes with our problem statements. A histogram best explains that for the attributes in both data sets with ratings given from 0 to 5, how much is the count of each star in each attribute. This also gives an idea which attributes were ranked higher in stars than the others and which attributes did poorly. The histogram of these attributes are below:
Data set 1

 <img width="465" alt="Screen Shot 2024-06-18 at 10 41 23 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/7fd568ff-9dad-443c-9463-8492d9cbf6cc.jpg">

Data set 2:

<img width="443" alt="Screen Shot 2024-06-18 at 10 41 41 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/5546355a-6829-4639-b5e5-3c58050773f4.jpg">

Secondly, we calculated the correlation score of these attributes with satisfaction and plotted a regplot to visualize this information as well as to see what attributes have most impacted the satisfaction score and what type of relationship do they share with the target variable.
Data set 1:

<img width="468" alt="Screen Shot 2024-06-18 at 10 42 02 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/6feb28ac-ee7a-4633-b7ce-71f944ee1b6f.jpg">

Data set 2:
 
<img width="341" alt="Screen Shot 2024-06-18 at 10 42 14 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/97e0ceeb-b475-410f-a6c5-58a48ab7d662.jpg">

<img width="570" alt="Screen Shot 2024-06-18 at 10 42 29 PM" src="https://github.com/Zarmin-dot/Customer-Satisfaction-for-Air-Travel/blob/main/images/5c16cf09-f3a0-461d-a51d-42c9db6a4cf7.jpg">

## Define your classification or prediction variables
In the first data set, the classification variable is the first column with the name ‘satisfaction’. This column tells whether each customer was satisfied or not with the airline based on the attributes mentioned in the first dataset.
For the second dataset, our classification variable is the column ‘Overall satisfaction’ where we have two labels; satisfied and non satisfied. This column initially had rating values from 0 to 5. As mentioned above, users that gave a rating of 4 or 5 are classified as satisfied; all the others have been classified as not satisfied.
