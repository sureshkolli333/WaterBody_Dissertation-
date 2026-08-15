# Water-Body Segmentation from Satellite Imagery

## Dissertation Project

**Title:** Evaluating Deep Learning Models for Water-Body Segmentation from Satellite Imagery and Human Evaluation on Unseen Images

**Author:** Suresh Kolli 

**Student ID:** 34046492

**Project Type:** MSc Dissertation

**Primary Task:** Water-Body Segmentation from Satellite Imagery

**Best-Performing Model:** ResUNet

**Primary Evaluation Metric:** F1-score

---
# Dataset Link : https://www.kaggle.com/datasets/franciscoescobar/satellite-images-of-water-bodies 

## 1. Project Overview

This project evaluates deep learning models for water-body segmentation from satellite imagery. The main purpose is to identify water and non-water regions at pixel level and determine which of the selected segmentation architectures provides the strongest performance under consistent experimental conditions.

The project evaluates four deep learning architectures:

1. U-Net
2. Fully Convolutional Network (FCN)
3. ResUNet
4. Attention Residual U-Net

The models were trained and evaluated using paired satellite images and corresponding water-body segmentation masks. After quantitative evaluation, the best-performing model was applied to previously unseen satellite images. Human evaluation was then used as an additional practical assessment of the quality of the generated segmentation outputs.

The project therefore follows a complete workflow:

Dataset preparation
Image and mask preprocessing
Dataset splitting
Model implementation
Model training
Quantitative evaluation
Best-model selection
Unseen satellite image evaluation
Human evaluation
Discussion of results
Limitations and future work

## 2. Aim

The aim of the project is to evaluate deep learning models for accurate water-body segmentation from satellite imagery, determine the best-performing model using Accuracy, Intersection over Union (IoU), Dice Coefficient and F1-score, and further assess its performance on unseen satellite images through human feedback.

## 3. Research Question

How effectively can the selected deep learning models segment water bodies from satellite imagery based on multiple evaluation metrics, and how accurately can the best-performing model segment water bodies in unseen satellite images based on human feedback?

## 4. Objectives

The project addresses the following objectives:

1. Prepare and preprocess satellite images and their corresponding segmentation masks to establish a consistent dataset suitable for water-body segmentation.

2. Design, implement and train U-Net, Fully Convolutional Network (FCN), ResUNet and Attention Residual U-Net models for pixel-level water-body segmentation.

3. Evaluate the segmentation performance of the four implemented models using Accuracy, IoU, Dice Coefficient and F1-score.

4. Determine the best-performing model by analysing its results across the selected evaluation metrics and generate segmentation predictions for previously unseen satellite images.

5. Validate the practical quality of the selected model's predictions by collecting and analysing human feedback on water-body segmentation outputs produced from unseen satellite images.

## 5. Dataset

The project uses the Satellite Images of Water Bodies dataset available through Kaggle.

Dataset characteristics:

Number of image-mask pairs: 2,841
Satellite image dimensions: 256 x 256 x 3
Segmentation mask dimensions: 256 x 256 x 1
Segmentation task: Binary segmentation
Classes: Water and non-water

Each satellite image has a corresponding segmentation mask. The mask identifies the water and non-water regions required for supervised pixel-level segmentation.

The dataset is suitable for this project because the images and masks are paired, allowing the models to learn the relationship between satellite image features and their corresponding water-body regions.

## 6. Data Preprocessing

The preprocessing stage was designed to establish consistent image and mask representations before model training.

The main preprocessing activities included:

1. Image resizing

All satellite images were standardised to 256 x 256 pixels.

2. Mask preparation

The corresponding segmentation masks were prepared for binary water and non-water classification.

3. Normalisation

Image values were prepared in a consistent numerical range for model training.

4. Training augmentation

Augmentation was applied to the training data to provide additional variation during model learning.

5. Dataset organisation

The paired images and masks were separated into training, validation and testing data.

The training set contained 2,044 image-mask pairs. The validation data was used to monitor model performance during training, while the independent test set was retained for final quantitative evaluation.

## 7. Experimental Design

All four models were evaluated using consistent experimental conditions. The same image dimensions, preprocessing procedures, dataset partitions, training configuration and evaluation measures were maintained so that differences in results could primarily be assessed in relation to the model architectures.

The models performed binary pixel-level segmentation, where each pixel was classified as either water or non-water.

The selected architectures were:

### 7.1 U-Net

U-Net uses an encoder-decoder structure with skip connections between corresponding encoder and decoder stages. The architecture was included as a strong baseline for pixel-level segmentation and is suitable for preserving spatial information and boundary details.

### 7.2 Fully Convolutional Network

FCN performs semantic segmentation using fully convolutional layers and generates dense pixel-level prediction maps. It was included as a different segmentation architecture and reference model.

### 7.3 ResUNet

ResUNet combines the U-Net structure with residual blocks and residual connections. The residual structure supports deeper feature learning while the U-Net-style skip connections help retain spatial information.

### 7.4 Attention Residual U-Net

Attention Residual U-Net combines residual learning with attention mechanisms. Attention gates are used to focus on relevant encoder features while residual blocks support feature learning and refinement.

## 8. Software and Experimental Environment

The implementation was mainly completed using Google Colab and Python.

The principal software and libraries used were:

Python
Google Colab
TensorFlow
Keras
NumPy
Pandas
OpenCV
Matplotlib

Google Colab was used as the cloud-based development environment for running the deep learning experiments.

TensorFlow and Keras were used to implement and train the four segmentation models.

NumPy was used for numerical array operations.

Pandas was used for dataset organisation and analysis.

OpenCV was used for image and mask preparation.

Matplotlib was used to visualise satellite images, segmentation masks, training results and model predictions.

The same software environment and experimental procedures were maintained across the four models.

## 9. Model Training

The four models were trained using 256 x 256 x 3 input images.

The task was defined as binary segmentation:

Water pixel = target region
Non-water pixel = background region

The training data contained 2,044 image-mask pairs.

The validation set was used to monitor training performance.

The independent test set was retained for final evaluation.

The same training configuration was used for the four architectures to maintain consistency across the experimental evaluation.

## 10. Evaluation Metrics

Four principal evaluation metrics were used:

Accuracy
Intersection over Union (IoU)
Dice Coefficient
F1-score

### 10.1 Accuracy

Accuracy measures the proportion of correctly classified pixels across the water and non-water regions.

Accuracy = (TP + TN) / (TP + TN + FP + FN)

### 10.2 Intersection over Union

IoU measures the spatial overlap between the predicted water region and the reference water region.

IoU = TP / (TP + FP + FN)

### 10.3 Dice Coefficient

The Dice Coefficient measures the similarity between the predicted segmentation and the reference segmentation.

Dice = 2TP / (2TP + FP + FN)

### 10.4 F1-score

F1-score provides a balance between precision and recall.

F1 = 2 x (Precision x Recall) / (Precision + Recall)

The F1-score was treated as the principal performance metric in the project because it provides a balanced indication of correct water-pixel identification and incorrect predictions.

## 11. Confusion-Matrix Terms

The segmentation evaluation uses the following terms:

TP: True Positive. A water pixel correctly predicted as water.

TN: True Negative. A non-water pixel correctly predicted as non-water.

FP: False Positive. A non-water pixel incorrectly predicted as water.

FN: False Negative. A water pixel incorrectly predicted as non-water.

These components support the calculation of Accuracy, Precision, Recall, F1-score, IoU and Dice Coefficient.

## 12. Quantitative Results

The final evaluation identified ResUNet as the best-performing model.

Final ResUNet results:

Accuracy: 90.96%
IoU: 74.47%
Dice Coefficient: 85.28%
F1-score: 85.28%

ResUNet achieved Rank 1 in the final model selection.

The final results indicate that ResUNet was able to identify water regions effectively and produce strong spatial agreement with the reference segmentation masks.

The F1-score of 85.28% was particularly important because it provided the principal balanced measure of segmentation performance.

## 13. Model Selection

The best-performing model was selected using the combined results from Accuracy, IoU, Dice Coefficient and F1-score rather than relying on only one measure.

ResUNet was selected because it produced the strongest overall performance within the experimental evaluation.

Its architecture combines residual blocks with U-Net-style skip connections. The residual connections support feature learning, while skip connections preserve useful spatial information required for water-body boundaries and fine structures.

The selected ResUNet model was therefore carried forward to the unseen-image evaluation and human evaluation stages.

## 14. Unseen Satellite Image Evaluation

After the quantitative model evaluation, the selected ResUNet model was applied to satellite images that were not used during the model development process.

The purpose of this stage was to examine how the selected model performed on previously unseen imagery.

The unseen-image evaluation showed that the model produced strong segmentation results for some images. However, the performance was not uniform across every satellite scene.

One reported example achieved 77% accuracy, 0.61 IoU and 0.75 Dice.

These results indicate partial generalisability. The model can produce useful segmentation outputs on unseen imagery, but changes in scene characteristics can affect segmentation quality.

Potential factors include differences in water-body shape, boundaries, surrounding land features, shadows and other visual characteristics.

## 15. Human Evaluation

Human evaluation was conducted after the selected ResUNet model generated segmentation outputs for unseen satellite images.

A total of 100 participants assessed the segmentation outputs.

Each participant evaluated five factors:

1. Segmentation accuracy
2. Completeness
3. Boundary quality
4. Visual quality
5. Overall quality

Each factor was rated on a 1 to 5 scale, where:

1 = Very poor
2 = Poor
3 = Average
4 = Good
5 = Excellent

The human evaluation provided an additional practical assessment because some visual characteristics of segmentation quality may not be fully represented by numerical metrics.

## 16. Human Evaluation Results

The aggregated human evaluation results were:

Segmentation accuracy: 4.70/5
Completeness: 4.83/5
Boundary quality: 4.72/5
Visual quality: 4.74/5
Overall quality: 4.78/5

Overall mean rating across the five factors:

4.75/5

Participant scores ranged from 4.60 to 5.00.

The results indicate that participants generally considered the generated segmentation outputs accurate, complete and visually satisfactory.

The high completeness rating indicates that participants considered the predicted outputs to cover the visible water regions effectively.

The strong boundary-quality rating indicates that the water boundaries were generally considered clear.

## 17. Overall Findings

The main findings of the project are:

1. Four deep learning segmentation architectures were successfully implemented.

2. The dataset contained 2,841 paired satellite images and segmentation masks.

3. All models were evaluated under consistent experimental conditions.

4. Accuracy, IoU, Dice Coefficient and F1-score were used as quantitative evaluation measures.

5. F1-score was selected as the principal performance metric.

6. ResUNet achieved the strongest overall model performance.

7. ResUNet achieved 90.96% Accuracy.

8. ResUNet achieved 74.47% IoU.

9. ResUNet achieved 85.28% Dice Coefficient.

10. ResUNet achieved 85.28% F1-score.

11. ResUNet was selected for evaluation on unseen satellite imagery.

12. Unseen-image results demonstrated strong performance in some scenes but variable performance across different scenes.

13. Human evaluation involved 100 participants.

14. Human evaluation covered five predefined factors.

15. The overall human evaluation mean was 4.75/5.

16. The quantitative and human evaluations together provided evidence of the practical quality of the selected segmentation outputs.


## 18. Reproducibility

To reproduce the main workflow:

1. Open the project in Google Colab.

2. Install or import the required Python libraries.

3. Load the Satellite Images of Water Bodies dataset.

4. Verify the paired image and mask files.

5. Resize images and masks to the required dimensions.

6. Prepare binary segmentation masks.

7. Organise the dataset into training, validation and testing partitions.

8. Implement the four selected architectures.

9. Train U-Net.

10. Train FCN.

11. Train ResUNet.

12. Train Attention Residual U-Net.

13. Evaluate each model using Accuracy, IoU, Dice Coefficient and F1-score.

14. Identify the strongest model.

15. Apply the selected model to unseen satellite images.

16. Save and visualise the prediction outputs.

17. Conduct the human evaluation of the selected model's unseen-image outputs.

18. Calculate the mean scores for the five human-evaluation factors.

19. Analyse the quantitative and human-evaluation findings together.

## 19. Human Evaluation Data

The human evaluation dataset should contain the following fields:

Participant ID
Participant Name
Signature
Gmail
Segmentation Accuracy
Completeness
Boundary Quality
Visual Quality
Overall Quality
Additional Comments

The five rating fields should use the 1 to 5 scale defined in the methodology.

Participant information should be handled according to the approved ethical and data-management procedures. The README describes the evaluation structure and does not treat generated or test identities as evidence of actual participant recruitment.

## 20. Ethical Considerations

The satellite imagery used for model development was obtained from a publicly available dataset.

Human evaluation was conducted as a separate assessment of segmentation outputs on unseen satellite images.

Participant information and feedback should be collected, stored and handled according to the approved dissertation procedures.

Only the information necessary for the human evaluation should be retained, and participant data should not be disclosed unnecessarily.

The project should not claim that human evaluation results represent specialist remote-sensing expertise because the evaluation was based on participant visual judgement.

## 21. Limitations

The main limitations identified in the dissertation are:

1. The evaluation used one publicly available dataset containing 2,841 paired satellite images and masks.

2. The dataset may not represent all geographical regions, seasons and satellite conditions.

3. Only four segmentation architectures were implemented.

4. The unseen-image evaluation showed variable performance across different satellite scenes.

5. The human evaluation involved 100 student participants and represented visual judgement rather than specialist remote-sensing expertise.

6. The study did not evaluate every possible satellite source, geographical environment or environmental condition.

These limitations should be considered when interpreting the results and the generalisability of the findings.

## 22. Future Work

Future development could investigate advanced segmentation approaches, particularly architectures using multi-scale feature fusion to preserve fine segmentation information while capturing broader contextual information.

Attention-enhanced segmentation could be further investigated to focus the model on relevant water regions.

Future work could also integrate optical and Synthetic Aperture Radar (SAR) imagery to provide additional information under challenging environmental conditions.

Multi-spectral and multi-source satellite imagery could be investigated to improve segmentation across different water-body conditions.

Semi-supervised or self-supervised approaches could also be explored to reduce dependence on large quantities of manually labelled masks.

Future experiments should use larger and geographically diverse datasets covering different seasons, regions and satellite sources.

The human evaluation could also be expanded to include participants with different levels of remote-sensing expertise and a wider range of evaluation scenarios.

## 23. Key Result Summary

The principal result of the project is:

Best-performing model: ResUNet

Accuracy: 90.96%

IoU: 74.47%

Dice Coefficient: 85.28%

F1-score: 85.28%

Primary metric: F1-score

Unseen-image evaluation: Strong results in some scenes with variable performance across different scenes

Number of human participants: 100

Human evaluation scale: 1 to 5

Human evaluation factors: Segmentation accuracy, completeness, boundary quality, visual quality and overall quality

Human evaluation overall mean: 4.75/5


## 26. Important Notes

The numerical results reported in this README are based on the final dissertation results provided for the project.

The principal selected model is ResUNet.

The F1-score is the main performance metric for interpreting the model results.

The human evaluation score of 4.75/5 is an aggregated practical assessment of the generated segmentation outputs and should be presented separately from the quantitative model metrics.

The unseen-image evaluation demonstrates that performance can vary across different satellite scenes. Therefore, the results should not be interpreted as evidence of universal performance across all satellite imagery.

The project should be evaluated using the complete experimental workflow rather than relying on a single metric or a single example image.
