---
title: "Securing cloud applications"
layout: post
---

Using Azure to build and host my own web application - securing it with a SSL certificate and applying Azure’s security features to protect it. 


 
### Technologies Used: 
 
Azure: (Keyvaults, App Services, Front Door, WAF) as well as PHP, HTML, Docker, OpenSSL
 
Developed and designed a web application using Azure’s cloud services and docker
Created and stored SSL certificates in Azure’s key vault and bound them to secure the web application
Protected the web application by utilising Azure’s security features, such as Azure’s Front Door, WAF and security center

### Requirements included:
 
* Deploying a docker container which had a framework for a blog webpage and sshing into the container to customise the webpage
* Creating a self signed certificate with OpenSSL 
* Storing the certificate in Azure’s key vault
* Binding the certificate to the website
* After determining the security issues with a self signed certificate, creating and bounding a managed CA approved certificate to the web application
* Deploying Azure’s front ddoor and configuring a WAF rule to restrict traffic from certain countries
* Analysing the Azure’s security center recommendations and applying the recommended fixes
 
### Advantages for choosing Azure’s app service resource instead of creating a virtual machine from scratch
 
Using Azure app service, I was able to pass the responsibility of managing features outside of the web application to the cloud service provider. I was only responsible for deploying and managing their web application and it's associated data
Deploying web applications can be done much faster as user's don't have to be concerned about configuring their OS
The user doesn't have to worry about the OS and middleware maintenance such as installing software updates and patching
Azure app services are cheaper to run than virtual machines
Azure app services have built in features for securing and hosting a web application, such as DNS, web app firewalls, domain purchasing and SSL certification binding
 
### Security issues encountered when using a self signed certificate
 
A self signed certificate is a certificate that has not been signed by a certificate authority. While these certificates are simple to create and have no expense, almost all browsers will alert the user visiting the webpage.
 
### Addressing the security concern
 
I created and bound a managed certificate provided by Azure, as this is a trusted certificate which had been approved by a CA which most browsers trust.
 
### Using Azure’s front door and its WAF feature
 
Azure’s front door is a cloud resource. It resides in front of my web application to protect it. It works on the application layer of OSI (Layer 7). Its primary solution is a load balancer. It can incorporate a WAF to protect against web vulnerabilities attacks. With the WAF, I applied a custom rule to protect against web requests from countries that I wasn't expecting any traffic from. This could help protect against potential attacks where I knew I wasn't expecting any visitors.
 
### Using Azure’s security center and applying its features
 
Azure Security Center is a management system that provides best practices and recommendations to enhance the security of your cloud resources. When I checked it, it had several security recommendations with various criticalities. One recommendation was to require FTP access into the web application with FTPS, which is the encrypted version of FTP.
