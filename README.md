# **Improving Water Well Quality in Tanzania**

**Authors:** _Hoang Nguyen, Ferit Yikar, Edel Prado_

<img src="images\cover.png" width=80%>

## Overview

<img src="images\UNICEF.png" width=30%>

## Business Problem

We are working with UNICEF to increase people`s water access in Tanzania. First we will identify status of current wells and plan to fix necessary wells as well as build new wells where needed. There are a lot of water wells in Tanzania. About half of them are either non-functional or needs repairing. We need to come up with a model that gives us the status of the wells. Using this model we can identify which wells need to be repaired. 

<img src="images\drivendata.png" width=50%>

***
## Data
We have a data from 59.400 water wells on which we made our model. This data consists of various specifications such as who built the well, where is the well located, when it was built and what is the quality/quantity of the water. We are trying to understand if we can predict the status of the well from these specifications. We then compare our best model to another data of 1111 wells to which we do not know the status of the wells. With this we can see how succesful our model is when predicting unseen data.

***
## Methods
This project uses various models to understand how our parameters affect the status of the wells. We built pipelines using knn model, decision tree model, random forest model, bagging model etc. and since our data was not equally distributed between functional, non-functional and needs repair wells we used SMOTE to create dummy rows that will result in a data set with equal ratios to each status. We compared the scores we get from different models to find the best one.
***
## Results


### Relationships of Features and Well Status
Our first step was to take a look at the relationships with well status within the dataset.


### Model
We ran more than 15 models to find the best model that predicts the well status. Although we had models that were more than 99% correct they did not show the same success on the unseen data. In order to prevent this overfitting we ran more models and built a model that shows similar results on both train and test data. Our best model (Bagging 500) predicted the unseen test data with a score of 81.10% in the Driven Data competition. The competition is going on for 7 years now and the best score is 82.94% 

<img src="images\Skylar_model.png" width=65%><br>

### Features of a Water Well
Our next process was to look at how much effect each feature has on the water well. We ran permutaion importance on our model to see how important our features are. Location of the well is by far the most important one, we will talk about location later. Another important aspect was the type of the waterpoint. For wells with long lifetime we recommend either using standpipes or hand-pump pipes based on where the well is located. If the water source of a well is higher, meaning well can use the gravity for extraction we recommend standpipes, if this is not possible hand-pump pipes are the best option.

<img src="images\Permutation_Feature_Importance.png" width=80%><br>
<img src="images\WaterPoint_Type.png" width=80%><br>
<img src="images\Extraction_Type_Class.png" width=80%><br>

### Location, Location, Location

We used our model and specifications to map how the wells are distributed in Tanzania. We than adjusted our findings for population to see how many wells are available per capita in different regions of Tanzania as well as how many non-functional wells. We used these maps to identify areas with low functional density and high non-functional and needs repair density. These areas are our first focus because there is need for wells in these regions and the wells have not been taken care of causing non-functional/functional ratio to increase.

Here you can see the status of wells based on what year they were built.


Functional Wells That Need Repair

<img src="images\functional_repair_well.PNG" width=80%>

Functional Wells

<img src="images\functional_well.PNG" width=80%><br>

Non-Functional Wells

<img src="images\non_functional.PNG" width=80%>


***
## Conclusion
This analysis gives us three recommendations for our Pump It Up prejoct:
- <u> How we can identify status of the wells in Tanzania? </u>
    - We can use our model which is 81% accurate on unseen data.
<br><br>

- <u>What features are most important when building new wells?</u>
    - We recommend UNICEF to build either standpipes that work with gravity or hand-pump pipes. Any other motor based pump will not have a long life.
<br><br>
- <u>Which areas should UNICEF focus on in this project?</u>
    - The circled areas on the map have high non-functional or needs repair wells and low functional wells. These areas should be our first concern.

***
## Next Steps
Further analyses could result with additional insights to further improve our recommendations:

- <u> We can improve our model? </u>
    - We ran into issues with computational power. There are other more complicated models that can be explored. With better computational power we can run more models to see if we can improve our results.
<br><br>
- <u> How non-functional are the welss? </u>
    - We can anayze non-functional wells to see which can be rebuilt nad which are gone for good.
<br><br>
- <u> We can use census changes to see how the need for wells change from region to region.</u>
<br><br>
- <u>Plan for the future.</u>
    - Population of Tanzania has been increasing rapidly for a while now. Instead of only planning for today we can get future prediction data for census and plan ahaed.
<br><br>
- <u>Analyze the problem.</u>
    - We can analyze the non-functional wells to see what went wrong. Get more data on the quantity of water to figure out why wells are becoming dry.


***
## For More Information
Please review our full analysis in our [Jupyter Notebook](./Main.ipynb) or our [presentation]().

For any additional questions, please contact

<img src="images\Hoang.png" width=10%> Hoang Nguyen: hvnguyen90@gmail.com <br />

<img src="images\ferit.png" width=10%> Ferit Yikar: yikarferit@gmail.com <br />

<img src="images\eddie.png" width=10%> Edel Prado: edel.prado.jr@gmail.com <br />


## Repository Structure

```
├── README.md                           
├── Main.ipynb   
├── Presentation.pdf 
├── notebooks  
├── data                                
└── images 
```
