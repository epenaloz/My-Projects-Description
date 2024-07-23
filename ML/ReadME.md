## Vertabal Column Data Set

In this assignment, I used K Nearest Neighbors, an ML algorithm for supervised learning.  For this assignment, I pre-processed the data, generated scatter plots and bar plots on the independent variables, created a K Nearest Neighbors algorithm for various metrics, and determined the lowest training error I received! My results are shown below. If you are interested in the data, you can find it here: https://archive.ics.uci.edu/dataset/212/vertebral+column

Grade: A+

![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/d2d172bf-ee8f-49e8-bc11-d9e7eb2e9e13)
![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/9539543b-d963-4f94-9bcd-0497542352cd)
![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/95cba810-e4fc-489b-98b0-60013d3ed0c5)


## Combined Cycle Power Plant Data Set
In this homework assignment, I implemented simple linear regression, multiple linear regression, pairwise interaction regression, polynomial regression, and quadratic nonlinearities. This assignment aimed to understand the change in the MSE on certain predictors/features and how it changes depending on the model or backward selection!

Grade: A

Here are some visualizations I created for this assignment. 

![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/099b965c-88cf-405b-a7c3-eddad1d708a6)
![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/e3c01d9d-309b-4a4f-9ea3-4154b7b4d908)

![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/f4941c78-f067-48ee-b781-3d4274475b0a)
![image](https://github.com/epenaloz/My-Projects-Description/assets/118321814/1e0ea61a-3beb-406a-a936-913242c51cbb)


## Time Series Classification:

Using the data set, the goal is to classify the activities of humans based on time series obtained by a wireless sensor network.

Information about the data: There are seven different types of activities in the data, and each contains 6-time series data collected: arg_rss12, var_rss12, avg_rss13, var_rss13, vg_rss23, ar_rss23. There are 88 instances in the data, each containing the six-time series data, and each time series data has 480 values.

Assignment:
Extracted time-domain features of the AReM dataset. I extracted minimum, maximum, mean, median, standard deviation, first quartile, and third quartile of all 6-time series in each instance of the data. Separated the data to testing and training. Using Bootstrap, I built a confident interval for the standard deviation of each feature. 

![Screenshot 2024-07-23 at 3 10 18 PM](https://github.com/user-attachments/assets/524329f6-8ce7-43fc-80e8-d35d1b29ccc9)

![Screenshot 2024-07-23 at 3 10 36 PM](https://github.com/user-attachments/assets/ab75073b-bb03-4c13-b5cf-b341783f6ec2)

Once the data was prepared, I performed a binary classification using logistic regression. The goal is to use the training set to classify the bending activity from other activities (a binary classification problem). 

![Screenshot 2024-07-23 at 3 11 07 PM](https://github.com/user-attachments/assets/8c5df8b5-f892-4a57-a617-0721848af676)


Using RFECV, Recursive Feature Elimination with Cross Validation (Stratified Cross Validation was used), it will recursively remove the least important features while using CV to determine the optimal number of features. I outputted the L,p, and accuracy values of the model. Where L is our training set broken into L = {0,1,2,…20} in equal lengths, and p values of the logistic regression parameters for each model. Then, I fit a logistic model with the pruned set of features obtained. 

The results are displayed below: the confusion matrix, ROC (TPR / FPR), and AUC (Area Under the Curve) of the classifier on the training data. 

![Screenshot 2024-07-23 at 3 14 55 PM](https://github.com/user-attachments/assets/dca8f11e-da2a-4e70-b89b-686f513bf7b6)

![Screenshot 2024-07-23 at 3 16 10 PM](https://github.com/user-attachments/assets/60f01dbc-9ece-4b6a-85d1-e7f4c6fd03da)

Now, we are testing the classifier on the test set. 

![Screenshot 2024-07-23 at 3 17 31 PM](https://github.com/user-attachments/assets/08e7a366-2a67-4fe5-bd2c-5c31175aba99)


Analysis: Our classes seem to be well-separated, which causes instability in calculating logistic regression parameters.
When attempting to obtain the coefficients using the logit model from stats, the error returned that the data was too well separated. To conclude, this causes a problem in our logistic regression modeling. Looking at the confusion matrix, you can see we have imbalanced classes, and there are more TN than TP. Why is this an issue? Because the "perfect" separation of classes can lead to extremely large TP or TN, which is seen in this case. This can result in convergence issues and issues with our coefficients.


Thus, we now use L1- penalized logistic regression! But first, I attempted to build a logistic regression model based on case-control sampling and adjust the parameters. The results are below for the training set. 

![Screenshot 2024-07-23 at 3 23 34 PM](https://github.com/user-attachments/assets/84044830-c57b-4c3f-9aca-94ef998b1069)

![Screenshot 2024-07-23 at 3 23 59 PM](https://github.com/user-attachments/assets/79e32cdd-3be0-40b2-bfcd-c4f1652224ca)

Now doing case sampling on the test set.

![Screenshot 2024-07-23 at 3 24 41 PM](https://github.com/user-attachments/assets/b2469439-ed6f-4e01-bbbf-c304a49c1a11)

We can now see the classes are better balanced.


After applying case-sampling, I applied L1-Penalized Logistic Regression to our data. (AKA Lasso regression). This will add a penalty to our coefficients. The results are below.

 ![Screenshot 2024-07-23 at 3 36 39 PM](https://github.com/user-attachments/assets/9c18b423-3da7-4a1b-8178-fce623cdb8f4)

![Screenshot 2024-07-23 at 3 37 24 PM](https://github.com/user-attachments/assets/12009fb5-9a31-4c44-9d10-81e4eb1ee182)

Since we have a multi-class classification case, I built an L1-penalized multinomial regression model to classify ALL activities in the training set. The results are below. 

![Screenshot 2024-07-23 at 3 40 32 PM](https://github.com/user-attachments/assets/51696fd6-f8d1-4238-b74a-434f4faac872)

![Screenshot 2024-07-23 at 3 41 30 PM](https://github.com/user-attachments/assets/5cca9433-eab3-4fa3-86cb-00d7fb517442)

Then, I ran a model using the Naive Bayes Classifier on the Gaussian and Multinomial models. The results are below.

![Screenshot 2024-07-23 at 3 42 50 PM](https://github.com/user-attachments/assets/782562fb-6ac3-4418-8ac4-835c7bd1a1c1)

![Screenshot 2024-07-23 at 3 42 57 PM](https://github.com/user-attachments/assets/027d6337-3e2a-4aa6-afe5-5e17f2a3460c)


Overall, this assignment aimed to classify time series using logistic regression, penalized logistic regression with L1, case sampling, understanding the unbalanced sample cases, and using Naive Bayes classifier. 


