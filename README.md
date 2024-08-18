# Predictive-Machine-Maintenance
Implementation of machine learning models to predict downtime and failures in manufacturing 

## Introduction
  Predictive machine maintenance is vital in the future of manufacturing because it allows for timely repairs to machines before failures occur. In this paper, I will demonstrate how common machine learning algorithms, such as decision trees and support vector machines, can be used in machine maintenance. Predictive maintenance is key in monitoring equipment and their conditions to more accurately predict when and what maintenance should be performed. This utilization of information can assist in minimizing downtimes, optimize resource allocation, and most importantly reduce maintenance costs. The main idea is to implement past maintenance data to predict equipment failures before those failures occur.
    	Predictive maintenance is important in multiple practical ways, such as allowing companies to schedule routine maintenance more accurately, avoid unwarranted delays, as well as extending the duration of use of the machines. It is also important in theoretical ways. For example, it can also lead to interesting breakthroughs in terms of data mining and machine learning techniques. It does this by forcing the analyses of multiple volumes of data, which can be unbalanced or even have missing values, which can then be utilized to develop predictive models.
    	One of the primary challenges is the minimal amount of research previously done that addresses domain-specific issues and provides solutions to those issues. While it has been studied to an extensive degree, there are still important needs that should address specific characteristics for varying industries while also attempting to improve predictive accuracy amongst the models.

## Data Resources

  The data that was used for the analysis was found by searching keywords such as “machine predictive maintenance” and “machine learning predictive maintenance”. The chosen data was found on Kaggle.com, which is an online data science competition community that has free available datasets to use. While not ideal, the data has been synthetically created to simulate machine usage along with fail states. This study  is just a demonstration on how machine learning models can be used on historic machine models.. So for the purpose of the study the synthetically generated data will suffice. 

## Steps for Cleaning

  There are not any missing data points in the set, but there are some structural errors. The data types of variables could be changed to better suit the information as well as some of the column names. The outliers of the data set were taken into consideration, but it was decided to leave the outliers in because they could be contributing to failures due to the machine failures being spare. The data for rotational speed is skewed, so a log transformation is warranted. The features being selected for our analysis are the product type (High, Medium and Low), torque, rotational speed, air temperature, process temperature and tool wear (minutes of use). 

## Methods

### Logistic Regression

The logistic regression model shows that every variable selected is statistically significant, except when the product type is of medium grade. A product grade of high was used a reference variable and is not included in this summary.The model has a high accuracy rate but has a low negative predictive value. The P-value for this model also shows that accuracy of the model is not statistically better than the no information rate, which is an accuracy that could be attained by always predicting the majority class.


### Decision Tree

The decision tree model also has high accuracy and sensitivity. It has a slightly lower specificity compared to the random forest model, but still higher than the logistic regression model. The random forest model has the highest AUC score among all models. A higher AUC score indicates better model performance, so the random forest model would be our choice of model to implement.

### Random Forest

The random forest model has high accuracy, sensitivity, and specificity. The p-value of the model does show that it is statistically better than the no information rate.

### Support Vector Machine

Unlike the previous methods where the models were predicting whether an error occurred or not, the SVM predicted the specific error that will occur. This will be useful to determine what maintenance will need to be done on the machines, which is the future of predictive maintenance. The model predicted the specific error with a 96% accuracy which is similar to the previous models discussed. The model tended to have false negatives which means that the machines would not be getting the maintenance that they need 4% of the time. This might become an issue when using real machine data. 

## Conclusion

With this study, it emphasizes the importance of determining predictive maintenance by utilizing past data to help determine potential failures before occurrences. This prediction can help save companies hundreds of millions of dollars in scrap parts, downed machine time, and tooling costs. With this study, it helped identify what the lynch pins were in the predictive maintenance model are which could then be used to implement failsafes or early detection models for machine failure. It was determined that one of the biggest contributing factors in machine failure is the quality of parts that are run through the machine. The lower the quality of parts, the higher the failure rate. Another coupling key factor contributing to machine failure is the air temperature and process temperature. Depending on the type of material being processed, both of the temperatures can impact the failure rate tremendously due to the porosity of that material. If the temperature is too low, the material has a higher chance of failure due to tooling breakages and if the temperature is too high, there is also a higher chance of failure due to overheating in machining parts. 

It was found that the random forest model was the optimal choice in determining predictive maintenance due to its versatility in usage. It can be applied to both classification and regression tasks as well as its high accuracy in determining predictions and variations. Since there were thousands of data points in the study, random forest also helps alleviate some of that noise level due to its input subletting capabilities. 


Looking into considerations or changes that we would implement for future projects, we would try to get actual data points from machining factories to be able to more accurately determine failure rates in real world scenarios. These are difficult to come by however, due to the exclusivity of this data to prevent competition from obtaining and copying the machining process being used by that specific company.
