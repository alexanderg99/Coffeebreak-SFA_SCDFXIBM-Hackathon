# Detailed Solution

## Contents

1. [Introduction](#introduction)
1. [Summary of Approach](#summary-of-approach)
1. [TP/FP Classifier](#tp-fp-classifier)

## Introduction

* Since 2018, smoke detectors have become mandatory in all residences. Given the inability of most smoke detectors to distinguish between smoke from real fires and smoke from innocuous sources, safeguards must be put in place to reduce false alarms. False alarms not only erode the trust of the public in fire safety systems, but will also cause precious resources to be wastefully mobilized in order to combat a non-existent threat.  

 * In order for fire alarm systems to be effective, people need to be able to trust what they hear. As long as people are convinced about the reliability of the fire alarm system, they will react to alarms with urgency, executing fire emergency protocols with haste. This will reduce casualties from any fire emergency.  

 * Furthermore, by comparing environmental data of occurring fire emergencies with that of past incidents, the SCDF would have a more accurate picture of the scale of the fire. This would allow SCDF to deploy a more appropriate amount of resources, potentially preventing overallocation of precious resources.  

## Summary of Approach

* Internet-of-Things (IoT) fire alarms can be gradually introduced to phase out the usage of old fire alarm systems. These IoT fire alarms will include sensors that capture meaningful data. This Big Data can then be utilised to train a neural network model for fire detection. On top of that, if visuals are available on the site of incident, image classification can be employed to detect the presence of a fire more confidently. This can be done using Convolutional Neural Networks (CNN) to extract features from the images obtained by visual feeds.  

* In order to prevent our model from making the wrong classification, which could potentially delay response to incidents, we propose an N-gram like model to account for changes in the situation with respect to time. An N-gram like model would mean that probability is evaluated repeatedly, hence reducing the possibility of wrong classifications. 

* Apart from fire detection, gauging the severity of the fire at incident sites can be crucial as well. As we have finite resources and manpower for firefighting and lifesaving, it is imperative to maximise its utility. As such, we have proposed the following idea to maximise the allocation of resources. 

* To enhance SCDF’s ability to gauge a fire’s severity, we propose to gather data from IoT sensors, which comprises of environmental factors like density of human traffic and location. These data will then be fed into our neural network models to train and eventually help predict the level of threats posed by fires while also mapping a safe evacuation route to allow victims to escape safely from the incident site. 

* All in all, an optimal deployment of resources plays a pivotal role in minimising the potential loss of lives and destruction of key infrastructures. 

## TP FP Classifier

* To construct a True Positive (TP), False Positive (FP) classifier, we will require a set of inputs that can accurately determine whether or not there is a fire. The most intuitive input would be images of the space around the smoke detector, such as snapshots of CCTV footage, which can be classified by means of a CNN. However, visuals are not available everywhere. A common scenario that comes to mind is smokers in public toilets. If a fire were to start due to this, a model dependent solely on visuals will be ineffective. 

* To prevent this issue, we consider the possibility of using sensor data as a possible input into our classifier. Example of potential inputs include CO levels, temperature, smoke density, humidity and spectral data (Infrared, UV light detection). Parameter tuning and feature testing will need to be done to strike a balance between cost and accuracy of classification.  

* Before moving on to the details of our classifier, we would like to take a moment to explain why a TP/FP classifier is needed. As mentioned in our analysis of problem statement, depending on the type of fire alarm installed, different systems will be vulnerable to different types of false positives. For instance, light-based smoke detectors will not be able to distinguish whether the smoke came from a fire, cigarette or incense, thus triggering indiscriminately under all 3 circumstances. Another example of current limitations would be heat detectors being triggered by innocuous activities such as cooking. The point of having multiple inputs is so that we can discover what combinations of these inputs can rule out certain harmless situations. This allows us to produce an accuracy probability estimate of whether a given set of inputs corresponds to a real fire. 

* In the situation without visuals, we can build a deep neural network to do classification, having a SoftMax layer as the output. In our output, TPs are represented by [1,0] and FPs are represented by [0,1], so the first entry in our output is the probability of being a TP, and the second entry in our output is the probability of being a FP, we then treat the situation as FP if it has a probability of <0.5. 

* The model is trained using binary-cross entropy as the loss function, and the specific structure of the model can be specified by an array. The model architecture can be customised as explained in the comments of tpfpclassifier.py. The reason we choose not to fix the architecture is because parameter tuning will need to be done to prevent over-fitting of the model. An example of what our program can generate is shown here:  

## Recommended Resources to be Deployed
