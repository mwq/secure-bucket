# Secure bucket



Sets up a bucket on s3 and an IAM user which only has accesss to the given bucket.
The command is idempotent and can be run multiple times. It creates bucket and user if they do not exist. It overwrites the policy if it already exist.

## Setup
You need a AWS credential file or AWS credentials in your ENV, with permission to create new users, buckets and policies.
See: http://docs.aws.amazon.com/cli/latest/userguide/cli-config-files.html

## Usage
```./bin/secure-bucket --bucket your-bucket-name --keys```

Skip ```--keys``` if you dont't want to regenerate new keys, otherwise the old keys will stop working. Outputs the access credentials to stdout if a new pair is generated.

Creates a bucket and a user with name your-bucket-name. The user will have access to the bucket and nothing more on your AWS account.
