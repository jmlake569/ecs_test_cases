# ECS Task Deployment for Custom Command Execution

This repository contains an AWS CloudFormation template and instructions for deploying a simple ECS task that runs custom commands using the Alpine Linux image. The ECS task is defined to execute specific commands on startup, making it suitable for various lightweight tasks or cron jobs.

The CloudFormation template included creates a basic ECS cluster with its own VPC, Subnets, roles, Security groups and a single task that runs commands you program in.

## Prerequisites

Before proceeding, ensure you have the following:

- An AWS account with appropriate permissions.
- AWS Command Line Interface (CLI) installed and configured.
- Basic knowledge of AWS ECS and Docker containerization.

## Customizing the Task Definition

1. **Clone this repository to your local machine**:

    ```bash
    git clone https://github.com/jmlake569/ecs_test_cases.git
    cd ecs_test_cases
    ```

2. **Edit the Task Definition JSON file**:

    - Open `task-definition.json`.
    - Replace the command in the `command` field with the command you wish to run.
    - Adjust the `cpu` and `memory` fields as needed for your command's requirements.

## Deploy Via AWS CLI

1. **Open a terminal and navigate to the directory containing the task definition**.

2. **Register the ECS Task Definition using the AWS CLI**:

    ```bash
    aws ecs register-task-definition --cli-input-json file://task-definition.json
    ```

3. **Create or Update your ECS Service to use the new task definition**.

## Running the Task Manually

To run the task manually:

1. **Open the AWS Management Console**.
2. **Navigate to the ECS section**.
3. **Select the appropriate cluster and task definition**.
4. **Run the task**.

## Deploying CloudFormation Template 

This template deploys everything required to run an ECS cluster that runs a single task. This cluster and template is for testing and development purposes only.

## Instructions

1. **Deploy using UI or CLI**.
2. **The paremter is not required and the default to a fake container image. You can include your own image here if you want, if not it defaults to an alpine container**.

## Stopping the Task

To stop the task, navigate to the ECS section in the AWS Management Console, select the running task, and choose to stop it.

---

## Example Usage

This setup is particularly useful for running lightweight cron jobs or one-off tasks in a serverless environment. 

---

## Contributing

If you wish to contribute to this project, please submit a pull request with your proposed changes.

