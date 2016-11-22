# gretel.tech

To run on docker,

Replace `<host>` with domain name (ie gretel.tech)
```
docker run -e VIRTUAL_HOST=<host> \
-e LETSENCRYPT_HOST=<host> \
-e LETSENCRYPT_EMAIL=<email> \
-e S3_ACCESSKEY=<key> \
-e S3_SECRETKEY=<secret> \
-e S3_BUCKETNAME=<bucket> \
-e S3_BUCKETREGION=<region> \
-d --restart=always --name=<host>  -v `pwd`:/var/lib/ghost ghost
```

After creating an AWS S3 bucket and a user with permission to access that bucket,
1. Open the IAM console.
2. In the navigation pane, choose Users.
3. Choose your IAM user name (not the check box).
4. Choose the Security Credentials tab and then choose Create Access Key.
5. To see your access key, choose Show User Security Credentials. Your credentials will look something like this:
  ```
  Access Key ID: AKIAIOSFODNN7EXAMPLE
  Secret Access Key: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
  ```