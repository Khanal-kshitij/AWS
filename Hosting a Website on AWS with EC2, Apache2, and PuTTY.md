# Hosting a Website on AWS with EC2, Apache2, and PuTTY

## Step 1: Launch a Linux EC2 Instance (Ubuntu)

1. **Login to AWS Console**:
   - Go to [AWS Console](https://aws.amazon.com/console/) and log in.

2. **Launch EC2 Instance**:
   - Navigate to **EC2** and click **Launch Instance**.

3. **Choose an AMI (Amazon Machine Image)**:
   - Select **Ubuntu Server**

4. **Choose Instance Type**:
   - Pick **t2.micro**

5. **Configure Security Group**:
   - Create a security group with the following inbound rules:
     - **SSH** (port 22)
     - **HTTP** (port 80)

6. **Key Pair**:
   - Create a new key pair and download the `.ppk` file.

7. **Launch the Instance**.

---

## Step 2: Connect to EC2 Using PuTTY

1. **Open PuTTY**.

2. **Enter the Public IP of EC2**:
   - In **Host Name (or IP address)**, enter your instance's **public IP**.
   - Example: `eg. (13.45.589.25)`

3. **Load PPK File**:
   - In the left sidebar, navigate to **Connection > SSH > Auth**.
   - Click **Browse** and select the `.ppk` file.

4. **Open the Connection**:
   - Click **Open** and use `ubuntu` as the username when prompted.

---

## Step 3: Install Apache2 on the EC2 Instance

Update the package list and install Apache2:
```bash
sudo apt update
sudo apt install apache2 -y
```

## Step 4: Delete Default index.html and Create a New One
1. Navigate to the Apache directory:
   cd /var/www/html
2. Delete the default index.html:
   sudo rm index.html
3. Create a new HTML file:
   sudo vi index.html
4. Add your HTML code:
   - Example:
   ```
     <html>
       Hi, I am Himanshu.
     </html>
   ```
5. Save and exit.

## Step 5: Access Your Website
1. Open a Browser.

2. Visit Your Website:

   Enter your EC2 Public IP in the browser:
   eg. (13.45.589.25)
3. You should see your custom HTML page! 🎉