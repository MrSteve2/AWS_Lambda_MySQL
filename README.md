# AWS_Lambda_MySQL
How to setup a MySQL DB in AWS with access via Lambda Function.


1) First use the following to create a AWS RDS MySQL DB
```
aws rds create-db-instance \
    --db-instance-identifier MySQLForLambdaTest \
    --db-instance-class db.t2.micro \
    --engine MySQL \
    --allocated-storage 5 \
    --no-publicly-accessible \
    --db-name ExampleDB \
    --master-username username \
    --master-user-password password \
    --backup-retention-period 3 
```


```
aws lambda create-function \
--region us-east-1 \
--function-name   CreateTableAddRecordsAndRead  \
--zip-file fileb://./app.zip \
--role arn:aws:iam::382526372780:role/lambda-vpc-execution-role \
--handler app.handler \
--runtime python3.6 \
--profile adminuser
```

TODO - Create db instance using boto3
TODO - Create Lamdba function using boto3
TODO - Automate updating lambda function on commit/code changes

TODO - figure out how to use Security Groups, may not be needed for lambda the way I am using
  --vpc-config SubnetIds=comma-separated-subnet-ids,SecurityGroupIds=default-vpc-security-group-id \

