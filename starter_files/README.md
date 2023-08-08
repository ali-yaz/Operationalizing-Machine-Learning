# Operationalizing Machine Leargning Project - Udacity

This project entails a comprehensive machine learning endeavor within the Microsoft Azure framework. I established a cloud-based production model for machine learning, successfully deploying and utilizing it. Employing the Bank Marketing Dataset, I trained a machine learning model by harnessing the advanced AutoML capabilities of Azure Machine Learning Studio. The next step involved deploying this model to a production environment through Azure Container Instance (ACI), subsequently accessing it via REST endpoints. Moreover, I engineered, made accessible, and employed a streamlined pipeline to automate the entire sequence of actions.

## Architectural Diagram

![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/b453da54e39c7f0dadf01c2dd186e179d600da87/sample_screenshots/diagram.PNG)
## Architecture Overview

The diagram above illustrates the step-by-step flow of operations. Let's dive into each phase:

1. **Register the Dataset**: Begin by uploading the dataset into Azure Machine Learning Studio. You can accomplish this either by providing a URL or uploading directly from a local folder.

2. **AutoML Execution**: Configure parameters such as compute cluster settings, classification task type, exit criteria, etc. Multiple models are trained on the uploaded dataset based on these configurations.

3. **Optimal Model Deployment**: Choose the most effective model from the AutoML run and deploy it into production. This deployment can be performed using either Azure Container Instance (ACI) or Azure Kubernetes Service (AKS).

4. **Logging and Application Insights**: Activate this feature either during initial model deployment or later via a Python script. It assists in tracking the deployed model's performance and recording successful/failed requests.

5. **Consumption of Model Endpoints**: After deploying the model, a REST endpoint is generated. This enables other services to interact with the deployed model by sending requests and receiving predictions as responses.

6. **Pipeline Creation and Publication**: Utilize the Azure Python SDK and a Jupyter Notebook to create and publish a pipeline. A `config.json` file in the working directory is necessary for this process. Pipelines automate the complete cycle of model training and deployment.

## Key Steps
## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
