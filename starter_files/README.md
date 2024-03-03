*NOTE:* This file is a template that you can use to create the README for your project. The *TODO* comments below will highlight the information you should be sure to include.

# Deploying an end-to-end MLOps solution with AzureML - Udacity ML Engineer with Azure Nanodegree
# Tony Patton 3/3/2024

This project allowed me to demonstrate the ability to create an end-to-end ML solution:
- including training a ML model using Azure AutoML
- deploying the best performing model as a REST endpoint for inference
- publishing the training pipeline as an endpoint as well in order to retrain the model if needed.

## Architectural Diagram
##
*TODO*: Provide an architectual diagram of the project and give an introduction of each step. An architectural diagram is an image that helps visualize the flow of operations from start to finish. In this case, it has to be related to the completed project, with its various stages that are critical to the overall flow. For example, one stage for managing models could be "using Automated ML to determine the best model". 

## Key Steps
##
- The first step required me to register the bank marketing dataset that has been used as a toy dataset.
![Alt text](https://github.com/aspatton/nd00333_AZMLND_C2/blob/master/screenshots/registered_dataset.png?raw=true)
- I created a new AutoML experiment that would run in a compute cluster that I created for that purpose.
- 
- I then selected the best performing model, in this case a weighted average of several models, and deployed it as a REST endpoint using an Azure Container Instance (ACI).

- I enabled Application Insights once the deployment was healthy through the python SDK in order to retrieve logs.

- I deployed locally a swagger container and started a python server for the swagger UI to access the swagger.json file. I was then able to access and fiddle with the deployment's REST API docs.

- I used a python script to consume the model endpoint by launching inference requests and parsing the json output to retrieve the inference result.

- I published the training pipeline to the workspace, and activated its endpoint so that we can trigger a pipeline run request
- Finally, we executed the pipeline and check that it had been succesfully re-run.


## Screen Recording

Youtube.com link

## Standout Suggestions

- We could probably improve the training step. The goal of this module was to learn MLOps and we thus disregarded crucial steps in model training, such as controlling the perfomance of the model over external sets, or using a validation set.
- I would have liked to explore different flavors of deployment, such as using AKS, real-time and batch deployments...
- Finally, something I'd also like to checkout is the usage of rules for automatic retraining rather than a scheduled retrain. Also monitoring for dataset drift, and other crucial steps of MLOps. The fact that the dataset is static is also something that would be great to change. Make it dynamic, expandable... as any dataset tends to be once we gather extra data!
