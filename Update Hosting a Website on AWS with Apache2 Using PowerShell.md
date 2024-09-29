# Hosting a Website on AWS with Apache2 Using PowerShell
 ## (These are the steps after launching instance and downloading .pem passkey)

**Step 1: Connect to EC2 Instance Using PowerShell**
 Open PowerShell in Windows.
 
 Navigate to your PEM file: First, ensure you’re in the directory where your .pem file is located. Use cd to change directories:
 
 cd path\to\your-pem-file

Use the ssh command to connect to your EC2 instance:

ssh -i "your_key.pem" ec2-user@your_instance_public_IP

Replace path_to_your_key.pem with the location of your private key.

Replace your_instance_public_IP with the public IP of your EC2 instance.


**Step 2: Update the Package List on Your EC2 Instance**

Run the following command after logging in to update your packages:

sudo apt update


**Step 3: Install Apache2**

 To install the Apache2 web server:
 
 sudo apt install apache2
 

**Step 4: Delete the Default index.html and Create Your Own**

 Navigate to the Apache web directory:
 
 cd /var/www/html
 

Delete the default index.html file:

sudo rm index.html


Create a new index.html file:
sudo vi index.html

Add your website's HTML content and save the file.
Your link or IP adress of your instance will now work.
