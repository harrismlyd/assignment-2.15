# Assignment-2.15

1. What is needed to authorize your EC2 to retrieve secrets from the AWS Secret Manager?

2. Derive the IAM policy (i.e. JSON)?

3. Using the secret name prod/cart-service/credentials, derive a sensible ARN as the specific resource for access

# Answers 

1. An IAM role that has permission to access Secrets Manager needs to be created.
This IAM role will be attached to the EC2 instance.
A policy for the IAM role needs to be created to allow permissions to read the secrets.

2.

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "secretsmanager:GetSecretValue",
                "secretsmanager:DescribeSecret"
            ],
            "Resource": [
                "arn:aws:secretsmanager:ap-southeast-1:m3l415072023:secret:DynamoDBPassword",
                "arn:aws:secretsmanager:ap-southeast-1:m3l415072023:secret:APIToken"
            ]
        }
    ]
}

3. arn:aws:secretsmanager:ap-southeast-1:m3l415072023:secret:prod/cart-service/credentials
