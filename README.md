# hello-world-lambda

## Build and Upload
Be sure to zip up the lambda using the `build.sh` file.

You can upload the lambda to an S3 bucket using the `deploy.sh` script.

## Usage in terraform script

```
resource "aws_lambda_function" "hello-world" {
  function_name = "HelloWorld"
  s3_bucket     = "lambda-deploy-hello-world"
  s3_key        = "hello-world.zip"
  handler       = "index.handler"
  role          = "${var.lambda_execution_role_arn}"
  runtime       = "nodejs14.x"
}
```