# Build a ML Workflow For Scones Unlimited On Amazon SageMaker

This project is a part of the assessment in Udacity's AWS Machine Learning Engineer Fundamentals Nanodegree Program.

## Project Overview

In this project, AWS SageMaker was used to build an image classification model that distinguishes bicycles from motorcycles. The model was deployed using AWS Lambda functions for supporting services, and AWS Step Functions to orchestrate the model and services into an event-driven application.

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
