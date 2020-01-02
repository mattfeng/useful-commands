# Useful commands and related programming things

## AWS Lambda Functions

### Files
* `lambda_function.py`
  * `lambda_request(event, context)`

### Installing external libraries
* `pip install -t . <library>`

### Compressing code and uploading to AWS
* `zip -r upload.zip .`
* `aws lambda update-function-code --function-name <name> --zip-file fileb://<file.zip>`

