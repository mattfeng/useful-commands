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


## GPG

### Generating a key
* `gpg --full-generate-key`

### Encrypting a message with your recipient's public key
* `gpg -o enc.gpg -e --sign --armor -R <recipient> <file>`
* Note: `<recipient>` must be in your public keyring.


## Useful Tools
* **forever**. Turn scripts into daemons on Linux.
