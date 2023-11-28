1) Create the source bucket
aws cloudformation deploy --template-file source-bucket.yml --stack-name source-bucket-chathra --region ap-southeast-1
2) upload the files to source bucket
zip -r wordpress-single-instance.zip source
3) Copy the source.zip to s3 bucket.
aws s3 cp wordpress-single-instance.zip s3://code-pipeline-source-bucket-chathra --region ap-southeast-1
