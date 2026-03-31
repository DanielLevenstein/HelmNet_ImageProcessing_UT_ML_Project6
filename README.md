# **Problem Statement**

## **Business Context**

Workplace safety in hazardous environments like construction sites and industrial plants is crucial to prevent accidents and injuries. One of the most important safety measures is ensuring workers wear safety helmets, which protect against head injuries from falling objects and machinery. Non-compliance with helmet regulations increases the risk of serious injuries or fatalities, making effective monitoring essential, especially in large-scale operations where manual oversight is prone to errors and inefficiency.

To overcome these challenges, SafeGuard Corp plans to develop an automated image analysis system capable of detecting whether workers are wearing safety helmets. This system will improve safety enforcement, ensuring compliance, and reducing the risk of head injuries. By automating helmet monitoring, SafeGuard aims to enhance efficiency, scalability, and accuracy, ultimately fostering a safer work environment while minimizing human error in safety oversight.

## **Objective**

As a data scientist at SafeGuard Corp, you are tasked with developing an image classification model that classifies images into one of two categories:

- **With Helmet:** Workers wearing safety helmets.
- **Without Helmet:** Workers are not wearing safety helmets.

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
| ---------- | -------- |
| Model 1    | 0.953125 |
| Model 2    | 0.578125 |
| Model 3    | 0.984375 |
| Model 4    | 1.000000 |

## Model Deployment

The final model from this project has been deployed on HuggingFace with a StreamLit API:
https://huggingface.co/spaces/DanielLevenstein/Helmet_Image_Classification

### Prediction Threshold

The initial project uses a prediction threshold of .95% This was intended to counteract the low quality test data provided as part of the project and was later removed once better data was found. 

## Conclusion

The HelmNet model successfully learns to detect helmets within the training distribution and achieves high accuracy on the evaluation dataset. When tested against 500 randomly sampled images from the original dataset, the model misclassified only one image, indicating strong performance on data similar to the training set.

However, additional testing on out-of-distribution images revealed an important limitation. The model tends to incorrectly classify construction workers who are not wearing helmets as "helmet present." This behavior is likely caused by dataset bias in the training data. Many helmet images in the dataset include additional contextual signals such as construction environments, safety vests, or worker poses. As a result, the model sometimes associates these contextual features with the presence of a helmet rather than detecting the helmet itself.

This highlights a common challenge in computer vision systems: neural networks may learn correlated features rather than the intended visual object if the dataset does not sufficiently represent counterexamples.

# **Actionable Insights**

Future improvements to the model would focus on expanding the dataset with additional “hard negative” examples, including:

- Construction workers without helmets
- Construction scenes without safety equipment
- Individuals wearing non-helmet headwear such as caps or hoodies

Increasing the diversity of the training dataset should help the model learn the true visual characteristics of helmets and improve generalization to real-world conditions.
