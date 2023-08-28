---
layout: distill
title: Worker Fatigue Classifier
description: Predicting Fatigue Levels Using Brainwave Data and Machine Learning
img: /assets/img/Proj_EEG/brain.jpeg
importance: 1
category: Tech
related_publications:
bibliography: Proj_EEG.bib
noDistHeader: true
---

# Predicting Fatigue Levels Using Brainwave Data and Machine Learning


<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_EEG/brain.jpeg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

In the realm of cutting-edge technology, the potential of machine learning is gradually seeping into various real-world applications. Among the myriad possibilities, one particularly intriguing avenue is its role in safeguarding the well-being of workers by monitoring their fatigue levels. This unique project harnesses the power of machine learning, brainwave data, and sophisticated devices to accurately predict an individual's fatigue state. In this article, we delve into the intricate details of this project, exploring its motivation, methodologies, and potential industry applications.

## Abstract
Machine learning, although still in its early stages of practical adoption, demonstrates a promising potential in real-life scenarios. One such scenario revolves around ensuring worker safety and productivity by gauging their levels of fatigue during their tasks. Leveraging the capabilities of wearable electroencephalograms (EEGs), this project involved recording EEG data from both fatigued (with less than 4 hours of sleep) and non-fatigued individuals. The collected data underwent a series of preprocessing steps, feature generation techniques, and Principal Component Analysis (PCA), culminating in the creation of images representing each state. Utilizing these resources, Artificial Neural Networks and Convolutional Neural Networks were trained to predict fatigue levels with remarkable accuracy, showcasing the potential of this innovative approach.

## Introduction
### Motivation
At the heart of this endeavor lies an intrinsic curiosity about the mechanics of Artificial and Convolutional Neural Networks (ANNs, CNNs) and the complexities they mirror from our own neural networks. This project emerges as an avenue to comprehend the intricate workings of the human mind while utilizing brainwave data for applications in artificial intelligence. By collecting and analyzing brainwave data, a unique opportunity is unveiled to bridge the gap between neural phenomena and advanced machine learning techniques.

### Project Goal
The central objective of this study was to harness the capabilities of machine learning models to predict an individual's fatigue state based solely on their brainwave data. Fatigue was defined as having less than 4 hours of sleep in the past 24 hours, while a non-fatigued individual had received at least 6 hours of sleep and felt well-rested. The Muse 2 device, originally designed as a meditation aid, was repurposed alongside the MindMonitor app to capture raw brainwave patterns and variations associated with sleep deprivation and well-rested states. By applying machine learning algorithms to this data, the models were able to accurately classify an individual's level of sleep deprivation.

## Industry Applications
### Enhancing Workplace Safety
The implications of this research extend into real-world scenarios, particularly within the manufacturing industry. In factory settings, where workers operate heavy machinery demanding full attention, the deployment of machine learning models could ensure that employees do not work while fatigued. Notably, sleep-induced fatigue contributes to a significant portion of workplace injuries and financial losses. By preventing fatigued workers from operating machinery, the manufacturing sector could potentially save millions of dollars annually.

### Averting Drowsy Driving Accidents
The significance of identifying fatigue transcends industrial domains. Consider the realm of road safety, where drowsy driving is a pressing concern. By enabling law enforcement to detect the likelihood of a driver falling asleep, the staggering number of accidents caused by drowsy driving could be significantly reduced. This approach has the potential to save lives and mitigate the economic burden associated with such accidents.

### Elevating Critical Professions
Industries relying on precision and critical decision-making, such as healthcare and construction, also stand to benefit from fatigue prediction. Nurses, doctors, and construction workers, tasked with safeguarding public safety, often work long hours and night shifts, making them susceptible to fatigue-related errors. Identifying fatigue levels in such professionals could enhance their performance and ensure optimal decision-making.

## Background and Overview
### Neural Oscillations Unveiled
Neural oscillations, characterized by repetitive patterns of neural activity in the Central Nervous System, serve as the foundation for this study. EEG bands, associated with specific behaviors and pathologies, are key indicators of brainwave patterns. These bands offer insights into various states of consciousness, laying the groundwork for the subsequent analysis.

### Data Collection
The Muse 2 device, renowned as a meditation aid, proves to be an unlikely protagonist in fatigue prediction. Outfitted with electrodes and sensors, it captures real-time brainwave activity, which when coupled with the MindMonitor app, facilitates data collection and analysis. The captured data reveals the nuances of brain activity during sleep deprivation and well-rested states, setting the stage for subsequent ML-based analyses.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_EEG/EEG_1.png" title="Muse 2" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Muse 2 device and associated EEG sensor locations.</div>

## Data Preprocessing and Feature Generation
### Unraveling Complex Data
Data preprocessing forms a critical bridge between raw data and machine learning models. The process involves refining the EEG readings, cleaning sensor data, and converting time formats for compatibility. The focus shifts to feature generation through Bird's <d-cite key="bird2018study"></d-cite> <d-cite key="bird2019mental"></d-cite> <d-cite key="bird2019deep"></d-cite> <d-cite key="ashford2019classification"></d-cite> [see note below] open-source Python method. This method transforms raw EEG readings into a rich set of 989 features through sliding window methods, each contributing to the intricate puzzle of fatigue prediction.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_EEG/Pipe.png" title="Data Pipe" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_EEG/Ex_Images.png" title="Sample Images" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Top: Overview of data pipeline. Bottom: Sample generated images from PCA components (upsampled for ease of visualization).</div>

{% details Details: Bird's EEG Feature Generation Code  %}
The present work heavily relies on Jordan J. Bird et. al.'s work in 2018, and 2019. The relevant code referenced in this section, as well as the relevant papers where it  is used in the literature, is [available here.](https://github.com/jordan-bird/eeg-feature-generation) The code was modified slightly in the present work.
{% enddetails %}

## Principal Component Analysis and Image Generation
### Transforming Data Dimensions
Principal Component Analysis (PCA) emerges as a powerful technique to reduce feature dimensions while preserving data essence. By condensing 989 features to 225 principal components, the dataset becomes more manageable and conducive to machine learning. Moreover, these components serve as the foundation for generating square ($$15^2 = 225$$) grayscale images, unlocking the convolutional power of neural networks. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_EEG/PCA.png" title="PCA Image Generation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">PCA Image generation.</div>

## Machine Learning Models
### Unveiling Predictive Potential
Several machine learning models take center stage in this study. Artificial Neural Networks (ANNs), Convolutional Neural Networks (CNNs), Random Forest, and Logistic Regression step into the spotlight to unravel the complexity of fatigue prediction. Each model showcases its unique strengths and limitations, with varying levels of accuracy and susceptibility to overfitting.

<div class="row justify-content-sm-center align-items-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_EEG/CNN_arch_t.png" title="CNN Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_EEG/CNN_gr.png" title="CNN Architecture" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">The architecture for one of our CNN models.</div>

## Results and Limitations
### Navigating Through the Findings
The study's evaluation through 3-Fold Cross Validation paints a picture of near-perfect accuracy across the models. However, this commendable performance is tempered by the specter of overfitting, stemming from the limited dataset size. The lack of variability and randomness in data collection limits the generalizability of results. While the models excel in distinguishing fatigue states within this constrained context, their true potential emerges in a larger, more diverse dataset.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/Proj_EEG/Res.png" title="PCA Image Generation" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">Cross-Validation (K=3) results for several tested ML algorithms. CNN uses image dataset, others use the same data in a flattened vector format.</div>

## Conclusion and Future Implications
### Pioneering a Path Forward
In the realm of brainwave data and machine learning, this project has illuminated a path toward predicting fatigue levels with impressive accuracy. The Muse 2 device, once confined to meditation practices, emerges as a potent tool for unraveling the intricacies of our neural activity. While the study's outcomes are promising, the potential lies in future iterations with expanded datasets, encompassing various forms of fatigue and more robust data collection. As technology advances and machine learning further integrates into our lives, the boundaries of possibility continue to expand, forging a future where fatigue prediction is a cornerstone of well-being and safety.

## Acknowledgements
This article presents work developed by the following authors:
1. Alberto Mussali
1. [Musa Habib](https://musa-habib.com/)
1. [Anant Goyal](https://anantgoyal.com/)
1. [Sadul Bombuwala](https://linkedin.com/in/sadul-bombuwala-6a556819b)

A big thank-you is more than due to our professor and supervisor for this project: [Ahmad Mohammadpanah.](https://mech.ubc.ca/ahmad-mohammadpanah/)
