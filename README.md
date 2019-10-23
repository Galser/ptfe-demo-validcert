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

- Prepare certificate -> The installer allows for using a certificate signed by a public or private CA. If you do not use a trusted certificate, your VCS provider will likely reject that certificate when sending webhooks. The key and X.509 certificate should **both be PEM (base64) encoded**.
> Note : Never save your certificate and private key in VCS (GitHUb or any other).
> Use any method to create certificates for appropriate name and prepare them soewhere in a sae private place, outside your VCS-controlled folders.
For this repo we have 2 files for the FQDN `ptfe-vagrant.guselietov.com`  : 
    ```bash
    ls -l ~/Certs/ptfe-vagrant.guselietov.com*
    -rw-r--r--  1 andrii  staff  1945 Oct 23 13:47 /Users/.../Certs/ptfe-vagrant.guselietov.com.cert.pem
    -rw-r--r--  1 andrii  staff  1676 Oct 23 13:47 /Users/.../Certs/ptfe-vagrant.guselietov.com.key.pem
    ```
    > Note 2, if you are using private CA (Certificate Authority ) then you also need to prepare CA Bundle. Terraform Enterprise needs to be able to access all services that it integrates with, such as VCS providers or database servers. Because it typically accesses them via SSL/TLS, it is critical that the certificates used by any service that Terraform Enterprise integrates with are trusted by Terraform Enterprise. A collection of certificates for trusted issuers is known as a Certificate Authority (CA) Bundle. All certificates in the certificate signing chain, meaning the root certificate and any intermediate certificates, must be included here. These multiple certificates are listed one after another in text format.

- Add proper domain record with the tools of your choice for your DNS provider pointin to IP-addres `192.168.56.22`. In this case - GoDaddy, via Web-console. Checking result :
    ```bash
    $ dig ANY ptfe-vagrant.guselietov.com

    ; <<>> DiG 9.10.6 <<>> ANY ptfe-vagrant.guselietov.com
    ;; global options: +cmd
    ;; Got answer:
    ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 18697
    ;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

    ;; OPT PSEUDOSECTION:
    ; EDNS: version: 0, flags:; udp: 4096
    ;; QUESTION SECTION:
    ;ptfe-vagrant.guselietov.com.	IN	ANY

    ;; ANSWER SECTION:
    ptfe-vagrant.guselietov.com. 3600 IN	A	192.168.56.22

    ;; Query time: 22 msec
    ;; SERVER: 192.168.2.254#53(192.168.2.254)
    ;; WHEN: Wed Oct 23 13:54:18 CEST 2019
    ;; MSG SIZE  rcvd: 72

    ```
- 


# Technologies

1. **To download the content of this repository** you will need **git command-line tools**(recommended) or **Git UI Client**. To install official command-line Git tools please [find here instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) for various operating systems. 
2. **For managing infrastructure** we using Terraform - open-source infrastructure as a code software tool created by HashiCorp. It enables users to define and provision a data center infrastructure using a high-level configuration language known as Hashicorp Configuration Language, or optionally JSON. More you encouraged to [learn here](https://www.terraform.io). 
3. **This project for virtualization** uses **AWS EC2** - Amazon Elastic Compute Cloud (Amazon EC2 for short) - a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. You can read in details and create a free try-out account if you don't have one here :  [Amazon EC2 main page](https://aws.amazon.com/ec2/) 
4. **Nginx stands apart - as it will be downloaded and installed automatically during the provision.** Nginx is an open source HTTP Web server and reverse proxy server.In addition to offering HTTP server capabilities, Nginx can also operate as an IMAP/POP3 mail proxy server as well as function as a load balancer and HTTP cache server. You can get more information about it  - check [official website here](https://www.nginx.com)  
5. **GoDaddy** - GoDaddy Inc. is an American publicly traded Internet domain registrar and web hosting company, headquartered in Scottsdale, Arizona, and incorporated in Delaware. More information here : https://www.godaddy.com/
6. **Let'sEncrypt** - Let's Encrypt is a non-profit certificate authority run by Internet Security Research Group that provides X.509 certificates for Transport Layer Security encryption at no charge. The certificate is valid for 90 days, during which renewal can take place at any time. You cna find out more on their [official page](https://letsencrypt.org/)


# TODO
- [ ] prepare step-by step instructions for installation part
- [ ] update README

# DONE
- [x] export GoDaddy keys/challenge responce
- [x] create domain entry
- [x] register certificate
- [x] update readme
- [x] prepare vagrant vm
