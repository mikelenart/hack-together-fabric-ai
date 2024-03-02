# hack-together-fabric-ai
This repository is used for the Microsoft Hack-Together-Fabric-AI Hackathon

This artical covers the following points:
The article covers the following points:

	•	Overview
	•	What is the Business Problem to be Solved?
	•	How the Solution Solved the Problem
	•	How the Solution Technically Works
	•	Video

# Overview
In this project, we are using Microsoft Fabric components to predict member disenrollment in health care plan. We aim to bring together various services of Microsoft Fabric to enable a seamless experience for Primary Care providers.

The services being used in this project are:

1. **Data Engineering** : Lakehouse, Notebook
2. **Data Factory** : Dateflow Gen 2, Data Pipeline
3. **Data Science** : Ml Model, Experiment, Notebook
4. **PowerBI** : Report

# What is the Business Problem to be Solved?
Often Health Care providers would like to track the disenrollment of members. This enables Health Care providers to tune their plans, provide best care and retain the members. 

# How the Solution Solved the Problem
This workflow provides a close-to-real-time tracking of "recent patient touch impressions" via PowerBI. 

1. As soon a recent patient touch is made by a care provider, data about the touch is loaded in the Lakehouse.
2. A scheduled data pipeline picks up the loaded information and runs through a prediction model. The prediction result is a prediction score indicating if a member will potentially disenroll in the future or not based on recent experience.
3. The prediction score is saved in a Lakehouse table.
4. The BI Report built on this table is updated. We can also set Alerts on BI Reports to send an email notification in case a threshold has reached.

The solution enables Primary Care Managers and decision makers with proactive and easy access to latest prediction scores.

# How the Solution Technically Works

![image](https://github.com/mikelenart/hack-together-fabric-ai/assets/61514817/b20267b9-721f-4e98-bce8-187c247c2e97)


1. A Care Provider loads latest "member touch data" in the Lakehouse
2. A data pipeline is scheduled to grab data from Lakehouse folder
3. Within data pipeline, a "metadata" checks if the file exists in the location
4. If success, trigger an ML notebook that uses a trained model, with input data as the uploaded file in the Lakehouse
5. Notebook generates a prediction score based on provided data, and loads the prediction scores in the Lakehouse Table
6. PowerBI report built on top of the Lakehouse Table where prediction scores are saved, is refreshed

# Power BI Dashboard

![image](https://github.com/mikelenart/hack-together-fabric-ai/assets/61514817/92e29a77-aba8-4d2e-ae3f-2568a23d6f24)



# Video

The demo video for submission is in the video folder of this REPO. Below is the link of the same:
![video link](https://github.com/mikelenart/hack-together-fabric-ai/blob/video_sub/video/Microsoft_fabric_hackathon_submission.mp4) 
