# Build a ML Workflow for Scones Unlimited on Amazon SageMaker

This project is part of the assessment in Udacity's AWS Machine Learning Engineer Fundamentals Nanodegree Program.

## Project Overview

In this project, **AWS SageMaker** is used to build an **image classification model** distinguishing bicycles from motorcycles. The model is deployed on an endpoint, and **AWS Lambda functions** support preprocessing and postprocessing. The entire workflow is orchestrated using **AWS Step Functions** for event-driven automation.

## Project Steps Overview

1. **Data Staging**  
   Prepare and organize the image data for training and validation.

2. **Model Training and Deployment**  
   Train the image classification model on SageMaker and deploy it as an endpoint.

3. **Lambdas and Step Function Workflow**  
   Create AWS Lambda functions for preprocessing, invoking the model, and postprocessing. Integrate these with AWS Step Functions to automate the workflow.

4. **Testing and Evaluation**  
   Test the deployed workflow and evaluate the model's performance.

5. **Optional Challenge**  
   (Extended or advanced tasks, if any.)

6. **Cleanup Cloud Resources**  
   Remove all AWS resources to avoid unnecessary charges.

## Building a State Machine via AWS Step Functions

- **Execution Flow of the Step Function:**  
  The state machine orchestrates the sequence of Lambda functions and model inference, handling both successful and unsuccessful inference outcomes.

- **Step Function Graphs:**
  - *Graph when inference threshold is met:*  
    The workflow proceeds to success and postprocessing steps.
  - *Graph when inference threshold is not met:*  
    The workflow branches to handle cases where the model's confidence is insufficient.

![Screenshot of working Step Function](Screenshot%20of%20working%20Step%20Function.png)
