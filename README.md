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
    Replace code with

https://github.com/ACloudGuru-Resources/course-aws-certified-developer-associate/edit/main/Serverless_Webite_Demo/hellocloudgurus.py

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

2.  Add Trigger -  API Gateway

mylambdafunction-API

https://us-east-1.console.aws.amazon.com/apigateway/main/api-detail?api=6hvavdmcyc&region=us-east-1#


Test via http 
    https://6hvavdmcyc.execute-api.us-east-1.amazonaws.com/default/mylambdafunction


```
Keep being awesome Cloud Gurus!
```

3.  Add S3  = Static webpage

https://github.com/ACloudGuru-Resources/course-aws-certified-developer-associate/blob/main/Serverless_Webite_Demo/index.html

xhttp.open("GET", "https://6hvavdmcyc.execute-api.us-east-1.amazonaws.com/default/mylambdafunction", true);

```
<html>
	<head>
		<script>
			function myFunction() {
				var xhttp = new XMLHttpRequest();
				xhttp.onreadystatechange = function() {
					if (this.readyState == 4 && this.status == 200) {
					document.getElementById("my-demo").innerHTML = this.responseText;
					}
				};
				xhttp.open("GET", "MY_API_GATEWAY_ENDPOINT_URL", true);
				xhttp.send();

			}

		</script>
	</head>
<body>
	<div align="center">
		<br>
		<br>
		<br>
		<br>
		<h1> <span id="my-demo">Hello Cloud Gurus!</span></h1>
		<button onclick="myFunction()">Click me</button>	
	</div>

	</body>
</html>
```


Test the serverless website

http://myserverlesswebsite-max.s3-website-us-east-1.amazonaws.com/


Hello Cloud Gurus! --> Keep being awesome Cloud Gurus!


