# AWS EC2 Setup Lab

This guide shows how to **launch and connect to your first EC2 instance** on AWS.  
It is designed for beginners who are learning cloud computing and want hands-on practice.

---

## Step 1: Log in to AWS
1. Go to [AWS Management Console](https://aws.amazon.com/console/).
2. Log in with your AWS account.
3. Navigate to **EC2 Dashboard**.

---

## Step 2: Launch an EC2 Instance
1. Click **Launch Instance**.
2. Select an **Amazon Machine Image (AMI)**:
   - Choose **Amazon Linux 2 AMI (Free Tier)**.
3. Choose **Instance Type**:
   - Select **t2.micro** (Free Tier Eligible).
4. Click **Next: Configure Instance Details**.

---

## Step 3: Configure Instance
1. Leave most settings as default for first setup.
2. Ensure **Auto-assign Public IP** is enabled (so you can connect remotely).

---

## Step 4: Add Storage
- Default storage (8GB) is enough for beginners.
- Click **Next: Add Tags**.

---

## Step 5: Add Tags (Optional)
- Click **Add Tag** and enter:  
  - Key: `Name`  
  - Value: `MyFirstEC2`

---

## Step 6: Configure Security Group
1. Create a new security group.
2. Add **Inbound Rule**:  
   - Type: SSH  
   - Protocol: TCP  
   - Port: 22  
   - Source: My IP (recommended)
3. Click **Review and Launch**.

---

## Step 7: Launch Instance
1. Click **Launch**.
2. Select **Create a new key pair**:
   - Name it `MyFirstKey`
   - Download `.pem` file (keep it safe!)
3. Click **Launch Instances**.

---

## Step 8: Connect to Your EC2 Instance
### On Mac/Linux:
```bash
chmod 400 MyFirstKey.pem
ssh -i "MyFirstKey.pem" ec2-user@<Public-IP>
