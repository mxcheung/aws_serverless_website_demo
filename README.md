# aws_serverless_website_demo
aws_serverless_website_demo


# Serverless deomo
Serverless demo using AWS Lambda


# Objectives
- Create a lambda function
- Create API Gateway to invoke lambda function
- Create Static website to invoke the lambda via API


# Cloud Guru

https://github.com/ACloudGuru-Resources/course-aws-certified-developer-associate/tree/main/Serverless_Webite_Demo


# Step by Step

1) Lambda  -->  Python 3.8 
    Replace codd with
    
```
def lambda_handler(event, context):
    print("In lambda handler")
    
    resp = {
        "statusCode": 200,
        "headers": {
            "Access-Control-Allow-Origin": "*",
        },
        "body": "Keep being awesome Cloud Gurus!"
    }
    
    return resp
```
