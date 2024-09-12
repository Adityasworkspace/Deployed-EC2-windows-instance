# Deployed-EC2-windows-instance
# EC2 Windows Instance Creation Guide

This repository provides a detailed step-by-step guide to creating an Amazon EC2 Windows instance using the AWS Free Tier.

## Prerequisites
- AWS Free Tier account
- Basic understanding of cloud computing and AWS services

## Step-by-Step Instructions

### Step 1: Sign In to AWS Management Console
1. Open the [AWS Management Console](https://aws.amazon.com/console/).
2. Sign in with your AWS account credentials. If you don't have an account, create one.

### Step 2: Navigate to EC2 Dashboard
1. In the AWS Management Console, navigate to the **EC2 Dashboard**.
   - You can find EC2 under "Compute" services or search for **EC2** in the search bar.

### Step 3: Launch an Instance
1. Click the **Launch Instance** button on the EC2 Dashboard.
2. You will be directed to the **Choose an Amazon Machine Image (AMI)** page.

### Step 4: Choose an Amazon Machine Image (AMI)
1. In the AMI selection screen, select **Microsoft Windows Server** from the list.
2. Ensure you select an AMI that is marked as **Free tier eligible**.

### Step 5: Choose an Instance Type
1. Select the **t2.micro** instance type, which is free tier eligible.
2. Click **Next: Configure Instance Details**.

### Step 6: Configure Instance Details
1. On the **Configure Instance Details** page, you can leave the default settings.
2. Ensure that **Auto-assign Public IP** is enabled (it should be enabled by default).
3. Click **Next: Add Storage**.

### Step 7: Add Storage
1. The default storage configuration is typically sufficient (30 GB of General Purpose SSD (gp2) is free tier eligible).
2. Adjust the storage size if necessary, but ensure it remains within the free tier limits.
3. Click **Next: Add Tags**.

### Step 8: Add Tags
1. Tags are optional but useful for organizing instances. You can add a **Name** tag to identify your instance.
   - Click **Add Tag**, and enter `Key: Name` and `Value: MyWindowsInstance` (or any preferred name).
2. Click **Next: Configure Security Group**.

### Step 9: Configure Security Group
1. Create a new security group or select an existing one.
   - For a new security group, provide a name and description.
2. Add rules to allow necessary traffic:
   - By default, an RDP (Remote Desktop Protocol) rule will be added to allow access from any IP (0.0.0.0/0). You can restrict this to a specific IP range for better security.
3. Click **Review and Launch**.

### Step 10: Review Instance Launch
1. Review all the settings you have configured.
2. Click **Launch** to proceed.

### Step 11: Key Pair for Authentication
1. A dialog will appear prompting you to select an existing key pair or create a new one.
   - Choose **Create a new key pair**.
   - Provide a name for the key pair (e.g., `MyKeyPair`).
   - Download the key pair file (.pem) and store it securely.
2. Click **Launch Instances**.

### Step 12: Access Your Instance
1. Once the instance is launched, go to the **Instances** page in the EC2 Dashboard.
2. Select your instance, and click **Connect**.
3. Follow the instructions provided to connect to your Windows instance using Remote Desktop.
   - You will need to use the key pair (.pem file) to decrypt the administrator password provided by AWS.

### Step 13: Connect to the Windows Instance
1. Use a Remote Desktop client (e.g., Microsoft Remote Desktop) to connect to your instance.
2. Enter the public IP address of your instance.
3. Use the decrypted administrator password to log in.

### Step 14: Terminate the Instance
1. When you no longer need the instance, terminate it to avoid any potential charges.
2. Go to the **Instances** page in the EC2 Dashboard.
3. Select the instance you want to terminate.
4. Click the **Actions** button, select **Instance State**, and then choose **Terminate**.
5. Confirm the termination when prompted.

---

## Additional Resources
- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/index.html)
- [AWS Free Tier](https://aws.amazon.com/free/)
