---
title: "Securing cloud applications"
layout: post
---

Using Microsoft Azure to build and host my own web application - securing it with a SSL certificate and applying Azure’s security features to protect it. 


 
### Technologies Used: 
 
Azure: (Keyvaults, App Services, Front Door, WAF) as well as PHP, HTML, Docker, OpenSSL
 
Developed and designed a web application using Azure’s Cloud services and Docker
Created and stored SSL certificates in Azure’s Key Vault, and bound them to secure the web application.
Protected the web application by utilising Azure’s Security features, such as Azure’s Front Door, WAF, and Security Center.

### Some of the important requirements included:
 
* Deploying a Docker container which had a framework for a blog webpage and sshing into the container to customise the webpage
* Creating a Self-signed certificate with OpenSSL 
* Storing the certificate in Azure’s Key vault
* Binding the certificate to the website
* After determining the security issues with a self-signed certificate, creating and bound a managed CA approved certificate to the web application
* Deploying Azure’s Front Door, and configuring a WAF rule to restrict traffic from certain countries
* Analysing the Azure’s Security Center recommendations and applying the recommended fixes
 
### Advantages for choosing Azure’s App Service resource, instead of creating a Virtual Machine from scratch
 
Using Azure App Service, I was able to pass responsibility of managing features outside of the web application to the cloud service provider. I was only responsible for deploying and managing their web application and it's associated data
Deploying web applications can be done much faster, as user's don't have to be concerned about configuring their OS
The user doesn't have to worry about the OS and middleware maintenance, such as installing software updates and patching
Azure App services are cheaper to run than Virtual machines
Azure App services have built in features for securing and hosting a web application, such as DNS, Web App Firewalls, Domain purchasing, SSL certification binding.
 
### Security issues encountered when using a self-signed certificate
 
A Self signed certificate is a certificate that has not been signed by a certificate authority. While these certificates are simple to create, and have no expense almost all browsers will alert the user visiting the webpage that is signed with a self-signed certificate that the webpage is not trusted by a Certificate Authority in the browser’s root store and to proceed with caution. 
 
### Addressing the security concern
 
I created and bound a managed certificate provided by Azure, as this is a trusted certificate which has been approved by a CA which most browsers trust.
 
### Using Azure’s Front Door and its WAF feature
 
Azure’s Front Door is a  Cloud Resource, it resides in front of my web application to protect it. It works on the Application Layer of the OSI Model (Layer 7). Its primary solution is a load balancer. It can incorporate a WAF to protect against web vulnerabilities attacks. With the WAF, I applied a custom rule to protect against web requests from countries that I wasn't expecting any traffic from. This could help protect against potential attacks where I knew I wasn't expecting any visitors.
 
### Using Azure’s Security Center and applying its features
 
Azure Security Center is a management system that provides best practices and   recommendations to enhance the security of your cloud resources. When I checked it, it had several security recommendations with various criticalities. One recommendation was to require FTP access into the web application with FTPS, which is the encrypted version of FTP.
