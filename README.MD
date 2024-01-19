# RMDY AI
*A Skin Disease Classifier utilizing Federated Learning*
___
## Table of Contents
 - [Federated Learning](#federated-learning)
 - [RMDY Structure](#rmdy-structure)
    - [How To Use RMDY as a Hospital](#how-to-use-rmdy-as-a-hospital)
    - [How To Use RMDY as a Data Scientist](#how-to-use-rmdy-as-a-data-scientist)
 - [Technologies Used](#technologies-used)
    - [Syft](#syft)
    - [Tensorflow](#tensorflow)
    - [ISIC](#isic)
 - [Summary](#summary)

## Federated Learning
Federated Learning is an approach to ML training increasing data security by flipping the standard model of training. Instead of sensitive data being entrusted and sent to data scientists, the data scientist's code is entrusted and sent to data owners who can securely train the AI model without exposing their data.

___

## RMDY Structure
The codebase of RMDY is split into two folders: one for Data Owners (hospitals, organizations), one for RMDY Devs (data scientists, researchers). Each folder has Jupyter Notebooks along with in-depth instructions on how to use them.

### How To Use RMDY as a Hospital
Hospitals will be sent the `Data Owner` folder. Hospitals must have computers/servers that can expose ports (port forward, proxy, reverse proxy, etc). One can use [ngrok](https://ngrok.com/) to temporarily and easily achieve this with minimal setup. The Data Owner creates a Federated Learning server (called a `Domain`), uploads their data to it, and grants Data Scientists limited access to the information.

Within the `Data Owner` folder is further instruction in the form of Markdown within the Jupyter Notebooks. The instructions assume that the Data Owners have minimal experience with code.

### How To Use RMDY as a Data Scientist
Data Scientists will be sent the `RMDY Devs` folder. Data Scientists must wait for Data Owners to start a `Domain` and create access for them. Data Scientists send a code request, which currently defaults to a simple Image Classifier, to the `Domain`.

Within the `Data Scientist` folder is further instruction in the form of comments within the Jupyter Notebooks. The instructions assume that the Data Scientists have moderate and higher experience with code.

___

## Technologies Used
> If I have seen further, it is by standing on the shoulders of giants - *Isaac Newton*
### [Syft](https://github.com/OpenMined/PySyft)
Syft is a library created to decentralize general data science programs and operations. Syft was the foundation we used to create for our implementation of Federated Learning.
### [Tensorflow](https://www.tensorflow.org/)
Tensorflow is Google's Machine Learning platform. We are training a Keras Image Classifer as the AI under the hood.
### [ISIC](https://www.isic-archive.com/)
The International Skin Imaging Collaboration​ (ISIC) is a training dataset we used extensively in the development of RMDY. It provided us invaluable filler data to test the limits of Syft, Tensorflow, and GPUs with large volumes of images.

___

## Summary
RMDY is a Skin Disease Classifier built on Keras Tensorflow. Syft was used to federate the learning of the Keras model. Combining Syft and Tensorflow was a challenge as Syft was not originally built to send Keras image and model data. Federating Learning legalizes and protects sensitive hospital data in the training of a public model for the good of the community.