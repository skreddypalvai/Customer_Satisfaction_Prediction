## **Happy Customers:**

### Background:

We are one of the fastest growing startups in the logistics and delivery domain. We work with several partners and make on-demand delivery to our customers. During the COVID-19 pandemic, we are facing several different challenges and everyday we are trying to address these challenges.

We thrive on making our customers happy. As a growing startup, with a global expansion strategy we know that we need to make our customers happy and the only way to do that is to measure how happy each customer is. If we can predict what makes our customers happy or unhappy, we can then take necessary actions.

Getting feedback from customers is not easy either, but we do our best to get constant feedback from our customers. This is a crucial function to improve our operations across all levels.

We recently did a survey to a select customer cohort. You are presented with a subset of this data. We will be using the remaining data as a private test set.

### **Objective:**

* The main objective of this project is to develop a predictive model that determines customer happiness based on the survey data. The dataset includes customer ratings for six different questions, which will be used to identify patterns and factors influencing customer happiness. By analyzing this data, we aim to build a robust model that can accurately predict whether a customer is happy or not ,insights gained from this analysis will enable the company to take actions to improve overall customer satisfaction and enhance operational efficiency.

### **Data Description:**

1. Y = target attribute (Y) with values indicating 0 (unhappy) and 1 (happy) customers
2. X1 = my order was delivered on time
3. X2 = contents of my order was as I expected
4. X3 = I ordered everything I wanted to order
5. X4 = I paid a good price for my order
6. X5 = I am satisfied with my courier
7. X6 = the app makes ordering easy for me

Attributes X1 to X6 indicate the responses for each question and have values from 1 to 5 where the smaller number indicates less and the higher number indicates more towards the answer.

### **Observations:**
*  Usually, when customers give high ratings, they are expected to be happy. However, it's important to note that in this dataset, some customers seemed unhappy even though they rated all six questions highly. This is evident in the 3rd and 4th rows. Additionally, there are no null values in the dataset.
  
![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/fb0621b1-3597-4560-be4c-8181baa5be9e) | ![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/a63b0558-2b76-470b-886e-2ae8c1b633a3)

*  Looking at the stats below, we notice that satisfied customers mostly gave a rating of 5 for the question "X1-My order was delivered on time". On the other hand, unhappy customers tended to give ratings of 4, 3, or 1 more often than the satisfied ones. It's interesting to see that both satisfied and unsatisfied customers gave nearly equal numbers of ratings (1, 2, 3, 4, and 5) for the "X2-Contents of my order was as I expected".

![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/c8440f6c-40ca-4939-a71c-4428f4684fe3)![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/04410023-3ada-455a-b9b4-eb4fd0281d8f)

*  We see that happy customers mostly rated question X3 ("I ordered everything I wanted to order") with 4 or 5 ratings, while unhappy customers gave it 1, 2, or 3 ratings. Similarly, for the question X4 ("I paid a good price for my order"), happy customers rated it with 4 or 5 ratings, whereas unhappy customers mainly gave it 2 and 3 ratings.

![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/483a0b52-bad6-43d0-a86f-928d617eb918) ![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/5b42f696-d940-4c63-8802-6ebac63f5ed5)

*  Happy customers mostly gave 5 ratings for the questions "X5-I am satisfied with my courier" and "X6-The app makes ordering easy for me".

![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/177935fa-928a-472e-9125-59672709e866) ![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/e0dca73f-d3b4-4abd-807c-501e054184b3)

*  Generally, when the correlation value is closer to +1, it shows a strong positive correlation. Conversely, if it's closer to -1, it suggests a weak negative correlation. Specifically, in this case, features X1, X5, and X3 display a strong positive correlation with the Target, with correlation values of 0.29, 0.21, and 0.18 respectively. However, features X2, X4, and X6 exhibit a weaker correlation with the target class.

![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/6f9006f1-e544-4aef-85eb-80fc56892f56)

*  After training the Decision Tree model with optimal hyperparameters on the data, it achieved an accuracy score of 61%. The recall score is 82%, indicating that the model correctly identifies 82% of happy customers but incorrectly labels 18% of them as unhappy. The precision score is 56%, suggesting a relatively high False Positive rate, meaning many unhappy customers are being incorrectly classified as happy. Additionally, through feature importance analysis, it's clear that the X2 and X5 feature is the least important. Based on the correlation value and feature importance, X2 is removed.

![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/f0370c8d-4d99-4608-a5ea-bcfc89c95131)![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/9057e6a2-fa52-4006-a643-776928decd39)

*  By fine-tuning the hyperparameters of the Random Forest Classifier model, it reached an accuracy of 65% and an F1 score of 64%, which is lower than the Decision Tree model. However, there's a notable difference in the feature importance between the Random Forest and Decision Tree models. It is clear that X3 and X1 have high feature importance score, followed by X6,X5 and X4.

![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/8cd47f1e-2afa-4a65-98ca-44ebb80f123a)![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/1c427daa-f0f9-4e94-8b6c-ae218563dcc3)

*  The Light GBM model achieved an impressive 74% accuracy score, which is higher than the previous two models. It also obtained an F1 score of 70%. The feature importance analysis shows that X1 and X3 are the two most important features, followed by X4.

![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/55881afd-55ae-4d6d-b367-6099d45761bc)![image](https://github.com/skreddypalvai/aKX3V0vGhGihpb1s/assets/137756791/645c536f-93ab-4be5-bf75-b62c5c0f7e9a)


In conclusion, after comparing the importance scores of all the three models, we find that X1, X3, X4 and X6 are the most crucial features. The logistic company can enhance customer satisfaction by giving top priority to these questions namely 'my order was delivered on time', 'I ordered everything I wanted to order', 'I paid a good price for my order' and 'the app makes ordering easy for me', while excluding X2 and X5 questions.
