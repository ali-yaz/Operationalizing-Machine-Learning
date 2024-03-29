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

## Authentication

- Authentication involves verifying users' identities and securely granting access to resources.
- While the course Workspace streamlined authentication, your personal Azure account requires additional steps.
- To interact with Azure Machine Learning Studio using the `az` command, install the Azure Machine Learning Extension.
- After installation, create a Service Principal account to manage authentication and associate it with your workspace.
- This ensures secure access to Azure resources during machine learning projects.

## Automated ML Experiment

- This phase configures an Automated ML (AutoML) run to automate training multiple machine learning models.
- Configuration includes specifying a compute cluster for model training resources.
- Define the machine learning task type, such as classification or regression, to guide AutoML.
- AutoML autonomously explores models and hyperparameters to identify the best performer.
- The result is a leaderboard ranking models by performance metrics, aiding model selection.

### Registered Dataset
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/a72b624f9e8bd725acfa12fc8f8a80f834955cb5/sample_screenshots/bankmarketing_dataset_registered.PNG)
### Model Training Completed
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/f7b4d27bc4709c03845170b00f19a6c1b5f9a1d2/sample_screenshots/model_completed.PNG)
### Best Model Summary
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/f7b4d27bc4709c03845170b00f19a6c1b5f9a1d2/sample_screenshots/best_model_summary.PNG)
## Deploy the best model
### Model deployed successfully
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/f7b4d27bc4709c03845170b00f19a6c1b5f9a1d2/sample_screenshots/model_deployed_successfully.PNG)
### Deploying the Optimal Model and Enabling Logging 
The most effective model derived from our AutoML iteration is launched into a production environment via Azure Container Instance (ACI). Through generated endpoints, our deployed model is made accessible for interactions with external services. Additionally, I implemented authentication during deployment, generating keys for secure authentication before engaging with the deployed model.
Following model deployment, I have the option to activate Application Insights, granting access to logs (this step is equally feasible during deployment).
### Model Deployed and Application Insights Enabled
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/app_insight_enabled.PNG)
### Log.py run 
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/log_py_run.PNG)
### 

## Swagger Documentation
Swagger is a tool I utilized for constructing and documenting REST APIs. It offers a platform for sharing documentation across product managers, testers, and developers, and can also be leveraged by various tools to automate tasks related to APIs.
Within Azure's framework, there exists a swagger.json URL that I employed to establish a web interface detailing the HTTP endpoint associated with a deployed model. I consumed the deployed model through Swagger, revealing the API's contents, as depicted in the screenshot below:
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/swagger_running_locally.PNG)
## Create and publish a pipeline
###  Create a Pipeline in the SDK
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/runwidget_1.PNG)
### Pipeline Created Successfully
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/pipelines_created.PNG)
### Pipeline endpoint
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/pipeline_endpoint.PNG)
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/bankmarketing_pipeline.PNG)
### Runwidget best model
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/bankmarketing_pipeline.PNG)
### Pipeline in Azure Studio
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/pipeline_endpoint.PNG)
###  Create the REST endpoint
![](https://github.com/ali-yaz/Operationalizing-Machine-Learning/blob/3411d5855f52d424f0ed0b730899d12a13a7e8ba/sample_screenshots/status_pipeline_active.PNG)
This is the REST endpoint in Azure ML Studio, with a status of ACTIVE.

## Screen Recording
Link to screen recording: https://youtu.be/6yAKk9MXyZ0
## Standout Suggestions
To enhance model performance, consider the following strategies:

1. Address the high data imbalance by implementing techniques that mitigate this issue, thereby enhancing model predictions.

2. Replace the accuracy metric with precision, recall, or AUC (Area Under the Curve) when evaluating model performance, especially for imbalanced data scenarios, as accuracy may not be an appropriate measure.

3. Explore the utilization of deep learning techniques, which can facilitate the training of multiple models and potentially result in improved model performance

