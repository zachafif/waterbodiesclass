# Water Bodies Identification using Sentinel-2
Portfolio project about Water Bodies Classification from Sentinel-2 Satellite Imagery 

## Introduction
Recent development in remote sensing and machine learning methods shows a new ways to delineate surface water bodies. As surface water monitoring is important in both ecological and hydrological studies. Remote sensing data could be utilized to construct a geographically permanent baseline for future comparisons, thus make it possible to create a time series monitoring. In this portfolio, I will build a classification model from several machine learning algorithms to classify water bodies from Sentinel-2 Dataset.

## Method
Method used in this portfolio shown in this figure,
![image](https://github.com/user-attachments/assets/abc82e29-6dc4-48de-a026-aa3b06b4a959)

### Area of Study
The area of study for this portfolio project is the urban area of Jabodetabek.

### Dataset
The dataset used in this project in Sentinel-2 (mosaic dataset) consist of only four out of twelve spectral bands available, which is Band 2, Band 3, Band 4, and Band 8. This dataset were downloaded from the Copernicus Hub.

![image](https://github.com/user-attachments/assets/375e312d-3a60-45e5-9530-616f1c10d455)

Another feature that being derived from this dataset are Normalized Difference Water Index (NDWI) and Normalized Difference Vegetation Index (NDVI) that calculated from the available bands using the following formula,

![image](https://github.com/user-attachments/assets/2ccc0836-2f22-4819-ac64-364265457ab5)

### Data Labelling (train-test)

We downloaded two separate satellite images for training and testing to make sure there are no data leakage. Then for each images, we create the label manually using QGIS,

![image](https://github.com/user-attachments/assets/cba4a79f-c908-4542-af40-4d0b4ddd1f9f)

### Modelling

We use four algorithms for this project, namely Random forest, XGBoost, Support Vector Machine, and Logistic Regression. All models in this portfolio use the default parameters.

## Result

Each model predicted the test dataset with the following result,

![image](https://github.com/user-attachments/assets/7e30b50c-dd17-4f14-962c-9000394ac2e5)

After that each model predicted into the wall to wall test dataset,

![Result](https://github.com/user-attachments/assets/daad19d2-2c89-4484-b84e-ee0d27aceaa6)

## Discussion

The modelling result in the test dataset shows a higher accuracy and F1 Score in ensemble models (random forest & XGBoost). Nevertheless, both SVM and logistic regression have results that are not too far from the ensemble models. However, when applied to wall-to-wall dataset, both ensemble models result in a fuzzy raster with a lot of vegetated area into water bodies.

![image](https://github.com/user-attachments/assets/632e8e35-b844-46d8-abfa-fb30163575f0)

This indicates that both ensemble models have overfitted, as it shows many misclassifications in the wall-to-wall dataset. Another possible reason for the misclassification is the label has less case of vegetated area.
