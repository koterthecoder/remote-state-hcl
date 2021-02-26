# Remote State VPC with Terraform

### update region, bucket, and dynamo table
```
terraform init -backend-config="bucket=S3_BUCKET" -backend-config="region=AWS_REGION" -backend-config="dynamodb_table=TABLE_NAME"
```