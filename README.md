# ptfe-demo-validcert
Install PTFE on Demo version with Valid Certificate - vagrant

# Purpose
Install PTFE on Demo version with Valid Certificate in Vagrantr environment, this repos contins the aprropiate Vagrantfile with instructions.

# Requirements

TFE Overview : https://www.terraform.io/docs/enterprise/index.html
Pre-Install checklist : https://www.terraform.io/docs/enterprise/before-installing/index.html

This repository assumes general knowledge about Terraform, if not, please get yourself accustomed first by going through [getting started guide for Terraform](https://learn.hashicorp.com/terraform?track=getting-started#getting-started). We also going to use Vagrant with VirtualBox and KitchenCI.

To learn more about the mentioned above tools and technologies -  please check section [Technologies near the end of the README](#technologies)

# How-to

# Technologies

1. **To download the content of this repository** you will need **git command-line tools**(recommended) or **Git UI Client**. To install official command-line Git tools please [find here instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) for various operating systems. 
2. **For managing infrastructure** we using Terraform - open-source infrastructure as a code software tool created by HashiCorp. It enables users to define and provision a data center infrastructure using a high-level configuration language known as Hashicorp Configuration Language, or optionally JSON. More you encouraged to [learn here](https://www.terraform.io). 
3. **This project for virtualization** uses **AWS EC2** - Amazon Elastic Compute Cloud (Amazon EC2 for short) - a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. You can read in details and create a free try-out account if you don't have one here :  [Amazon EC2 main page](https://aws.amazon.com/ec2/) 
4. **Nginx stands apart - as it will be downloaded and installed automatically during the provision.** Nginx is an open source HTTP Web server and reverse proxy server.In addition to offering HTTP server capabilities, Nginx can also operate as an IMAP/POP3 mail proxy server as well as function as a load balancer and HTTP cache server. You can get more information about it  - check [official website here](https://www.nginx.com)  
5. **GoDaddy** - GoDaddy Inc. is an American publicly traded Internet domain registrar and web hosting company, headquartered in Scottsdale, Arizona, and incorporated in Delaware. More information here : https://www.godaddy.com/
6. **Let'sEncrypt** - Let's Encrypt is a non-profit certificate authority run by Internet Security Research Group that provides X.509 certificates for Transport Layer Security encryption at no charge. The certificate is valid for 90 days, during which renewal can take place at any time. You cna find out more on their [official page](https://letsencrypt.org/)


# TODO
- [ ] export GoDaddy keys/challenge responce
- [ ] create domain entry
- [ ] register certificate
- [ ] update readme
- [ ] prepare vagrant vm
- [ ] prepare step-by step instructions for installation part
- [ ] update README

# DONE
