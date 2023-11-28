# AWS CloudFormation and S3 Pipeline Setup Instructions

Follow these steps to set up your AWS environment using CloudFormation and S3.

## 1. Create the Source Bucket

Deploy the `source-bucket.yml` template to create a new S3 bucket. This bucket will be used to store your source files.

```bash
aws cloudformation deploy \
    --template-file source-bucket.yml \
    --stack-name source-bucket-chathra \
    --region ap-southeast-1
```
## 2. Zip and Upload the source files to source bucket

```bash
zip -r wordpress-single-instance.zip source
```

```bash
aws s3 cp wordpress-single-instance.zip s3://code-pipeline-source-bucket-chathra --region ap-southeast-1
```
## 3. Deploy basic-pipeline.yml file to create the pipeline using Cloudformation template

