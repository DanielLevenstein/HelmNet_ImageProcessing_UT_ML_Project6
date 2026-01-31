# **Problem Statement**
## **Business Context**
Workplace safety in hazardous environments like construction sites and industrial plants is crucial to prevent accidents and injuries. One of the most important safety measures is ensuring workers wear safety helmets, which protect against head injuries from falling objects and machinery. Non-compliance with helmet regulations increases the risk of serious injuries or fatalities, making effective monitoring essential, especially in large-scale operations where manual oversight is prone to errors and inefficiency.

To overcome these challenges, SafeGuard Corp plans to develop an automated image analysis system capable of detecting whether workers are wearing safety helmets. This system will improve safety enforcement, ensuring compliance, and reducing the risk of head injuries. By automating helmet monitoring, SafeGuard aims to enhance efficiency, scalability, and accuracy, ultimately fostering a safer work environment while minimizing human error in safety oversight.
## **Objective**
As a data scientist at SafeGuard Corp, you are tasked with developing an image classification model that classifies images into one of two categories:
- **With Helmet:** Workers wearing safety helmets.
- **Without Helmet:** Workers not wearing safety helmets.
## **Data Description**
The dataset consists of **631 images**, equally divided into two categories:

- **With Helmet:** 311 images showing workers wearing helmets.
- **Without Helmet:** 320 images showing workers not wearing helmets.

**Dataset Characteristics:**
- **Variations in Conditions:** Images include diverse environments such as construction sites, factories, and industrial settings, with variations in lighting, angles, and worker postures to simulate real-world conditions.
- **Worker Activities:** Workers are depicted in different actions such as standing, using tools, or moving, ensuring robust model learning for various scenarios.
## Project Analysis
- In this project, four models were created to attempt to categorize employees as either wearing helmets or not.
- Based on my data analysis, I believe model 3 performed the best at accuracy of 98%

| Model Name | accuracy |
| --- | --- |
| Model 1 | 0.953125 |
| Model 2 | 0.578125 |
| Model 3 | 0.984375 |
| Model 4 | 1.000000 |

### Additional Observations
- The success_threshold used has a large impact on the final model accuracy scores.
- I initially used a success_threshold of 50% and then changed it to 95% to prevent overfitting. 
- Using too low of a value for success_threshold resulted in significant model overfitting.
- I believe that a value in between those two values is likely to result in the best results. 

# **Actionable Insights & Recommendations**
- Based on the model visualization for model 2 and model 3, it looks like model 3 is heavily overfit, so trying a version of model 2 with a success_threshold between 95% and 50% might make sense. 

