# AWS Configuration

Please, remember that you will have to assign to your Lambda function Role some permissions like:
 - Allow Lambda response to the API Gateway
 - Allow Lambda write on DynamoDB (Create, Update, Read and Delete)

## Lambda
 - Copy this directory files inside the Lambda function
 - Create a file named *.config* inside the *config/* folder with the next syntax:
```
TABLENAME=DynamoDBTableName
ENDPOINT=LINK_OBTAINED_FROM_THE_AWS_WEB_SOCKET_API_GATEWAY
```

## DynamoDB
 - Create a table

## API Gateway
 - Create an API Gateway of the type WebSocket API
 - On the *Route selection expression* type *request.body.action*
 - Create the routes:
   - $connect
   - $disconnect
   - $default
   - changeLight
   - connectUser
 - Use the Lambda integration type for the routes and select the Lambda function you just create
