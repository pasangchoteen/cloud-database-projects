# EC2 + MySQL Setup Instructions for Data Analysis

## Step 1: Launch EC2 Instance

1. **Log in to AWS Management Console** and navigate to **EC2**.
2. Click **Launch Instance** and choose **Ubuntu 20.04 LTS** as the operating system.
3. Select **t2.micro** as the instance type (free tier eligible).
4. Configure **Security Group** to allow the following:
   - **Port 22 (SSH)**: Open to your IP address.
   - **Port 3306 (MySQL)**: Open to your IP address or leave this restricted to your EC2 instance (for remote access).
5. Download and configure your **Key Pair**.

Once the instance is running, note the **Public IP** address of the EC2 instance.

## Step 2: SSH into EC2 Instance

1. Open your terminal (or use **PuTTY** on Windows).
2. Run the following command (replace `your-key.pem` with your key file and `ec2-public-ip` with your EC2 instance’s public IP):
   ```bash
   chmod 400 your-key.pem
   ssh -i "your-key.pem" ubuntu@ec2-public-ip
