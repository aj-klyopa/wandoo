# wandoo

### Introduction
Homework for DevOps Engineer position.
Using this code you are can create a webservice Whoami behind Nginx using SSL.
An SSL cetificate will be signed by Letsencrypt and will be automaticaly renewed.

### Usage


1. Set your servername/domainname in the .env file
   ```console
   MYDOMAINNAME=<your_domain_name>
   ```
2. Export variables
   ```console
   . .env
   ``` 
3. Start the servie
   ```console
   docker-compose up -d
   ```   
4. Create a certificate for securing webservice
   ```console
   docker-compose exec acme.sh --issue --server letsencrypt -d $MYDOMAINNAME -w /acme.sh 
   ```
5. Change keyfile's owner to grant access to the key from Nginx in Docker.
   ```console
   chown 101 acme.sh/$(echo "$MYDOMAINNAME" | tr '[:upper:]' '[:lower:]')_ecc/$(echo "$MYDOMAINNAME" | tr '[:upper:]' '[:lower:]').key
   ```
      
