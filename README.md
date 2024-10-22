# Multi-modal capabilities from Anthropic Claude on Amazon Bedrock for natural language query

## Introduction

Despite the advancement of foundation model, which can generate complex SQL statement, the main issue is the foundation model lacks the understanding of organization's data schema. Each organization has different naming convension, as such we need a way to feed the data schema and make the foundation model understands it. This repository provides the use case example of using Anthropic Claude's multi-modal capabilities to do **NLQ** (or Natural Language Query). By feeding the database's entity relationship diagram (or ERD) into image channel and user's question into text channel, Anthropic Claude foundation model can understand your data schema and use those information to generate the specific SQL according to the user's question.

This repository provides the end-to-end example from getting the user's question, generating SQL query, querying the data lake using Amazon Athena, and generating more natural outputs instead of table-like responses from Amazon Athena.

## AWS services involved

- **Amazon Bedrock**: access Anthropic Claude foundation model
- **Amazon S3**: store the sample dataset
- **Amazon Glue Data Crawler**: build the data catalog from the dataset in Amazon S3
- **Amazon Athena**: use for querying the dataset

## Prerequisite

- Understanding of `Python` programming language and `boto3` SDK, please see [here](https://boto3.amazonaws.com/v1/documentation/api/latest/reference/services/bedrock-runtime.html) for boto3 documentation
- Up-to-date `boto3` library (you can do this by `pip install --upgrade boto3`)
- Python IDE of choices to execute the code (alternatively, you can use SageMaker notebook instance, or SageMaker Studio for code execution)
- IAM role to access above AWS services on your behalf
- Access to Anthropic Claude on Amazon Bedrock, you can do this on Amazon Bedrock console page

![model access](https://github.com/aws-samples/Simplify-natural-language-query-with-Anthropic-Claude-on-Amazon-Bedrock/blob/main/img/bedrock-model-access.png?raw=true)
  

## Architecture Diagram

Below is the architecture diagram of this solution.

![architecture diagram](https://github.com/aws-samples/Simplify-natural-language-query-with-Anthropic-Claude-on-Amazon-Bedrock/blob/main/img/nlq-architecture-diagram.png?raw=true)


## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

