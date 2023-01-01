# AWS Lambda Empty Function Project (in C# .net6)

This starter project consists of:
* Function.cs - class file containing a class with a single function handler method
* aws-lambda-tools-defaults.json - default argument settings for use with Visual Studio and command line deployment tools for AWS

## Install AWS toolkit and setup profile

Install AWS Toolkit for VS 2022 https://aws.amazon.com/visualstudio/

Open AWS Explorer and create a default AWS profile

## Steps to follow from Visual Studio:

To deploy your function to AWS Lambda, right click the project in Solution Explorer and select *Publish to AWS Lambda*.

To view your deployed function open its Function View window by double-clicking the function name shown beneath the AWS Lambda node in the AWS Explorer tree.


## Steps to follow to get started from the command line:

Once you have edited your template and code you can deploy your application using the [Amazon.Lambda.Tools Global Tool](https://github.com/aws/aws-extensions-for-dotnet-cli#aws-lambda-amazonlambdatools) from the command line.

Install Amazon.Lambda.Tools Global Tools if not already installed.
```
    dotnet tool install -g Amazon.Lambda.Tools
```

If already installed check if new version is available.
```
    dotnet tool update -g Amazon.Lambda.Tools
```

Deploy function to AWS Lambda
```
    cd "aws_lambda1/src/aws_lambda1"
    dotnet lambda deploy-function
```

# aws-lambda-tools-defaults.json 
    This file provides default values for the deployment wizard inside Visual Studio and the AWS Lambda commands added to the .NET Core CLI

     "function-handler"     : "aws_lambda1::aws_lambda1.Function::FunctionHandler",
     "function-name"        : "Friendly_function_name" (Optional friendly name for the lambda)

     When publish create a user with AWSLambdaBasicExecutionRole which has CloudWatch Log writing permissions

# launchSettings.json 
    This file contains the profile for Mock Lambda Test Tool. This helps to test locally.
    AWS uses .net6 runtime for this project