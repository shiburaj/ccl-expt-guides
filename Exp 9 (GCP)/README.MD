# Experiment 9 : GCP
## Host your Portfolio Site on Google Cloud along with a Domain Name.
This guide will help you deploy a static website on a VM on Google Cloud Platform and Also connect with a Domain with SSL enabled

### Steps to Deploy

#### Prepare a Static Website
1. Prepare a Static Portfolio Website and upload it to Github

#### Create a VM Instance
1. Open [https://console.cloud.google.com](https://console.cloud.google.com) and Login
2. Create a Project and Attach a Billing
3. Go to Compute Enginer >> VM Instances
4. Click ```Create Instance``` Button
5. Complete the Below 7 sub steps to make a VM Instance
   1. Machine Configuration: Give a name to your VM, Select your region, Select appropriate machine type (E2-micro)
   2. OS and storage: Change OS to ubuntu
   3. Data Protection: no backups
   4. Networking: Allow HTTP and HTTPS
   5. Observability: no changes
   6. Security: no changes
   7. Advanced: no chnages
6. Click ```Create``` button

#### Assign Static IP for Instance
1. Search for IP Address in Search bar and find ```IP Addresses``` in VPC Networks
2. Find the Public IP that is assigned to the Instance
3. This IP is currently Ephemeral that means it may change after reboot so click on Three dots under Actions and click ```Promote to static IP``` and give a name 
4. Copy this Public IP and head on to your domain registrar where your domain is registered

### Setup A Records for your Domains
1. Open your Domain Registrar Panel
2. Find your domain name and update the DNS records
3. You need to add a new ```A``` Record with the Public IP from previous step and any suitable TTL (14400)

#### Install NGINX and Upload Code
1. Connect to the Instance using the ```SSH``` button under Connect and Install a Webserver to Serve your website
```
sudo apt update
sudo apt install nginx
```
2. Go the the following folder where the html files needs to be uploaded ```/var/www/html``` and delete all existing files with ```rm -rf *```
```
cd /var/www/html
rm -rf *
sudo git clone <your-repo-url> .
```
3. Open the website using the Public IP and also Try opening using the Domain Name too.

#### Configure NGINX for SSL and use Certbot
1. Open nginx default config file in ```/etc/nginx/sites-enabled/default```
2. Add your domain name in the server_name field
```
sudo nano /etc/nginx/sites-enabled/default
```
Go to Line 46 and change it from
```
server_name _
```
to 
```
server_name <your-domain-name>
```
3. Use ```Ctrl+O``` to save. Use ```Ctrl+X``` to Extit
4. Reload Nginx
```
sudo service nginx reload
```
5. Use Certbot to Get Free SLL certificate from LetsEncrypt
```
sudo apt install certbot python3-certbot-nginx 
sudo certbot --nginx -d <your-domain-name>
```
6. Complete the steps and your SSL will be installed