# Useful commands and related programming things

## AWS S3

### Setup S3 FUSE
* `sudo apt-get update`
* `sudo apt-get install automake autotools-dev fuse g++ git libcurl4-gnutls-dev libfuse-dev libssl-dev libxml2-dev make pkg-config`
* `git clone https://github.com/s3fs-fuse/s3fs-fuse.git`
* `cd s3fs-fuse && ./autogen.sh && ./configure --prefix=/usr --with-openssl && make && sudo make install`
* `touch /etc/passwd-s3fs`
* `vim /etc/passwd-s3fs`
* `ACCESS_KEY:SECRET_KEY`

### Mount S3 bucket as FUSE file system
* `s3fs <bucketname> -o use_cache=/tmp -o allow_other -o uid=1001 -o mp_umask=002 -o multireq_max=5 <mount_folder>`
* Will need to edit `/etc/fuse.conf` to allow others.

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


## Docker

### Start and run a container interactively
* `docker run -it <image> /bin/bash` (if no `ENTRYPOINT` defined)
* `docker run -it --entrypoint /bin/bash <image>` (if `ENTRYPOINT` defined)


## Ubuntu

### Find which version of a package will be installed
* `apt-cache policy <package>`

### Install a specific version of a package
* `apt-get install <package>=<version>`

## Useful Tools
* **forever**. Turn scripts into daemons on Linux.
