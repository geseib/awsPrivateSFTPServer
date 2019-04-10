# awsPrivateSFTPServer

## Overview
[AWS Transfer for SFTP](https://aws.amazon.com/sftp/ "AWS Service Page") is a fully managed service that enables the transfer of files directly into and out of Amazon S3 using the Secure File Transfer Protocol (SFTP)—also known as Secure Shell (SSH) File Transfer Protocol. In many cases it is desrable to have this service accessable externally from the internet, however there are also use-cases to have a private internal SFTP Server. THis Template helps setup the required VPC Endpoint to make this work.

## Running the template
The template assumes you have a VPC and two Subnets in two Availability Zones that you want to deploy into. When you deploy the SFTP server after, you will associate it with the VPC endpoint created here. The endpoint ID can be found in the Resources tab of the CLoudformation template once it has completed. The DNS address that you will be able to use to access the SFTP server is in the Output tab of the Cloudformation template. 


### Attached is a Demo Cloudformation template which gets you:
* Role for logging from Transfer Service (to be attached when creating SFTP Server)
* VPC Endpoint with two ENIs to be deployed in two Availability Zones (to be associated when creating SFTP Server)
* Security Group for attaching to VPCEndpoint (Should be scoped to where Clients are connecting from. In Prod this should be as specific a list as possible)
