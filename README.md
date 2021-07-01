# Custom Lambda Authorizer
A Lambda authorizer is useful if you want to implement a custom authorization scheme that uses a bearer token authentication strategy such as OAuth or SAML, or that uses request parameters to determine the caller's identity.
When a client makes a request to one of your API's methods, API Gateway calls your Lambda authorizer, which takes the caller's identity as input and returns an IAM policy as output.

# Steps
1. An API Gateway endpoint is invoked with a JWT token.
2. Before sending the request to the endpoint, API Gateway invokes the Lambda Authorizer for JWT token verification.
3. Lambda Authorizer checks the validity of the JWT token using custom code with an external authentication system.
4. If the JWT token is valid, the request is passed to the requested endpoint or explicitly denied if the JWT token is invalid.

# Custom Lambda Authorizer types:
- A token-based Lambda authorizer(`TOKEN` authorizer)
- A request parameter-based Lambda authorizer(`REQUEST` authorizer)

# Official docs & references
- [Main](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-use-lambda-authorizer.html)
- [Input Format](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-lambda-authorizer-input.html)
- [Output Format](https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-lambda-authorizer-output.html)
- [Configure a cross-account Lambda authorizer](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-lambda-authorizer-cross-account-lambda-authorizer.html)
- [Secure AWS API Gateway Using A Lambda Authorizer](https://medium.com/@sumindaniro/secure-aws-api-gateway-using-a-lambda-authorizer-40a1da825b16)
- [Token Based Authorization](https://github.com/awsdocs/amazon-api-gateway-developer-guide/blob/main/doc_source/apigateway-use-lambda-authorizer.md#example-create-a-token-based-lambda-authorizer-function)
- [Request Based Authorization](https://github.com/awsdocs/amazon-api-gateway-developer-guide/blob/main/doc_source/apigateway-use-lambda-authorizer.md#example-create-a-request-based-lambda-authorizer-function)

# Code
- [aws-apigateway-lambda-authorizer-blueprints](https://github.com/awslabs/aws-apigateway-lambda-authorizer-blueprints)
- [jwt-rsa-aws-custom-authorizer](https://github.com/auth0-samples/jwt-rsa-aws-custom-authorizer)
- [sam-api-gateway-request-auth](https://github.com/mavi888/sam-api-gateway-request-auth)