# wandoo

### Introduction
Homework for DevOps Engineer position.
Using this code you are can create a webservice Whoami behind Nginx using SSL.

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
      
