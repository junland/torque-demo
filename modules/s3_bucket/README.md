# S3 Bucket Terraform Module

This module creates an AWS S3 bucket with configurable ACL and tags.

## Usage

```hcl
module "s3_bucket" {
  source     = "./modules/s3_bucket"
  bucket_name = "my-unique-bucket-name"
  acl         = "private" # or other ACLs
  tags        = {
    Environment = "dev"
    Project     = "example"
  }
}
```

## Inputs
| Name        | Description                  | Type         | Default  |
|-------------|------------------------------|--------------|----------|
| bucket_name | The name of the S3 bucket    | string       | n/a      |
| acl         | The canned ACL to apply      | string       | private  |
| tags        | A map of tags for the bucket | map(string)  | {}       |

## Outputs
| Name       | Description           |
|------------|-----------------------|
| bucket_id  | The name of the bucket|
| bucket_arn | The ARN of the bucket |
