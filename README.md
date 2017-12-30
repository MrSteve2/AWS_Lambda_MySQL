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

TODO - Create using boto3

