# LambdaAPIDemo
    Create a Lambda API using Java 21 

1. Set Up Your Development Environment
    First, ensure you have the following installed:

    Java Development Kit (JDK)
    Apache Maven
    AWS CLI
    AWS Toolkit for Eclipse\IntelliJ (or your preferred IDE)

2. Create a New Maven Project
    Open your terminal and create a new Maven project:


    mvn archetype:generate -DgroupId=com.example -DartifactId=LambdaAPIDemo -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

3. Add Dependencies
    Navigate to your project's directory and update the pom.xml file to include the necessary dependencies:

refer pom.xml

4. Create the Lambda Function
    Create a new Java class for your Lambda function:

refer LambdaHandler class

5. Package the Lambda Function
    Package your Lambda function into a deployable JAR file:


6. Deploy the Lambda Function to AWS
    Use the AWS CLI to create the Lambda function. First, create a role with the necessary permissions:

7. Create an API Gateway
    Create a new REST API using the AWS Management Console, link it to your Lambda function, and deploy it. Here are the high-level steps:

    Go to the API Gateway console.
    Create a new REST API.
    Create a new resource and method (e.g., GET).
    Link the method to your Lambda function.
    Deploy the API.

8. Test with Postman
    Copy the invoke URL from the API Gateway console.
    Open Postman and create a new request.
    Set the request type to GET and paste the invoke URL.
    Send the request.

commands 
---------

1)  aws iam create-role --role-name lambda-basic-execution --assume-role-policy-document file://trust-policy.json
2) aws iam attach-role-policy --role-name lambda-basic-execution --policy-arn arn:aws:iam::aws:policy/service-role/AWSLambdaBasicExecutionRole
3) aws lambda create-function --function-name HelloLambda --zip-file fileb://target/LambdaAPIDemo-1.0-SNAPSHOT.jar --handler com.example.LambdaHandler --runtime  
   java21 --role arn:aws:iam::ACCOUNT_ID:role/lambda-basic-execution


