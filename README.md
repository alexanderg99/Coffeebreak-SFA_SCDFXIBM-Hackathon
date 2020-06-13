# Coffeebreak-Placeholder_SCDFXIBM

## Contents

1. [Short description](#short-description)
1. [The architecture](#the-architecture)
1. [Long description](#long-description)
1. [Getting started](#getting-started)
1. [Built with](#built-with)
1. [Contributing](#contributing)

## Short description

### Team details

Team name: Coffeebreak

Team members: 

* Alexander Gunawan
* Aloysius Wang
* Benjamin Lee
* Jasper Ong
* Vico Lee

### What's the problem?
* False alarms are a major inefficiency to any fire alarm system. When a fire alarm is falsely triggered, people may call in to SCDF to report non-existent fires, leading to wastage of resources and potentially curtailing SCDF's ability to target real threats. Frequent false alarms also lead to a loss of confidence in the system, leading to slow response in cases of actual fire. 

* It is important to quickly evaluate whether an alarm is a true positive or a false positive so that SCDF can respond to situations appropriately. 

### How can technology help?
* As part of the Smart Nation Sensor Platform initiative, there will be greater deployment of IoT and sensor technologies within the nation. Existing sensors that monitor air quality already exist, and can be expanded further to better respond to potential fires.   

* Internet-of-Things (IoT) technology can be installed into existing fire alarm systems for smarter detection of threats. These detection systems would be able to gather important data, allowing SCDF personnel to make informed decisions based on the ground situation and formulate strategic plans to fight the threat. 

* Using state-of-the-art artificial intelligence technology, like neural networks and Computer Vision, we can better analyse data gathered from smart systems, providing real-time support for SCDF personnel to swiftly act upon the danger with appropriate amount of resources while evacuating civilians safely from the threat in a timely and fashioned manner. 

* By using limited resources in a targeted and efficient way, SCDF will be able to handle more situations in a given period of time. 

### The idea
Deploying deep learning techniques to analyse data from past fire alarms, we can more accurately judge the severity of fires given environmental factors and sensor data. This will allow SCDF to make more informed decisions when allocating resources.  

## The architecture

![architecture.png](https://github.com/jasperosy/Coffeebreak-Placeholder_SCDFXIBM/blob/master/architecture.png)

1. When the fire alarm rings, the sensors in the fire alarm will record environmental data, storing it in a backend database. 
2. Severity rating is determined by performing classification on environmental data. 
3. If the alarm is determined to be a false alarm, an announcement will be made. 
4. If a real fire has broken out, SCDF will be notified. Severity rating will be used to recommend an appropriate amount of resources that should be deployed to combat the emergency.  

## Long description

[More detail is available here](DESCRIPTION.md)

## Getting started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites
Things you will need before running our code.
* Data-set
* Python 3 (with tensorflow and numpy installed)

### Installing
```bash
git clone https://github.com/jasperosy/Coffeebreak-Placeholder_SCDFXIBM.git
cd Coffeebreak-Placeholder_SCDFXIBM
python main.py
```

## Built with

## Contributing
Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.
