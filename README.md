
# **Project Introduction**

**Node-App Deployment** is a web-based application that runs using Node.js without requiring servers like Nginx or Apache HTTP Server, as Node has its own server.

This project follows a **monolithic architecture**, where the application and all dependencies are hosted on a single AWS EC2 instance, with PM2 used to run the app in the background.

# **1. Architecture Overview**

![myimage](/Images/ChatGPT_Image_Apr_25_2026_04_52_33_PM.png)

# 2. Instance Setup

## 2.1 Launch Instance

![Screenshot 2026-04-22 180556.png](/Images/Screenshot_2026-04-22_180556.png)

## 2.2 Names & OS

Name : `Node-Server`

OS : `Amazon Linux`

![image.png](/Images/image.png)

## 2.3 AMI & Instance Type

AMI : `Default`

Architecture : `Default`

Instance Type : `t3.micro` (2CPU & 1GB Memory)

![Screenshot 2026-04-22 180704.png](/Images/Screenshot_2026-04-22_180704.png)

## 2.4 Key & Network

Key : `Raj-Virginia-Key` (Exiting One)

Security Group : `Launch-Wizard-1` (Exiting One)

![Screenshot 2026-04-22 180721.png](/Images/Screenshot_2026-04-22_180721.png)

## 2.5 Start Instance

![image.png](/Images/image%201.png)

## 2.6 Connect

![image.png](/Images/image%202.png)

## 2.7 Copy SSH Client Link

![image.png](/Images/image%203.png)

# 3. Installing Packages

## 3.1 Open GitBash Where Your Private Is Stored(.pem)

![Screenshot 2026-04-22 180855.png](/Images/Screenshot_2026-04-22_180855.png)

## 3.2 Connect Instance With Public IP

```jsx
ssh -i Raj-Virginia-Key.pem ec2-user@54.161.38.170
```

## 3.3 Update Packages

```jsx
sudo yum update
```

## 3.4 Install Git

```jsx
sudo yum install git -y
```

## 3.5 Git Clone Repo

```jsx
git clone https://github.com/iamtruptimane/node-js-app-CICD.git
```

## 3.6 Install Node

```jsx
sudo yum install nodejs -y
```

## 3.7 View Git & Node Version

```jsx
git --version
node --version
```

# 4. Running Node App

## 4.1 Go To Directory Which Create Via Git Clone

```jsx
cd / node - js - app - CICD;
```

![image.png](/Images/image%204.png)

## 4.2 To View Start Script

```jsx
cat package.json
```

![image.png](/Images/image%205.png)

## 4.3 Inside Project Folder Install Dependencies

```jsx
sudo npm install
```

## 4.4 To Run App (FrontGround)

```jsx
node app.js

If Press Ctrl + C → App Stops
```

## 4.5 To Install PM2

```jsx
sudo npm install -g pm2
```

## 4.6 To Run App In BackGround

```jsx
pm2 start app.js
```

# 5. **Access** On Browser

## 5.1 To Add Port Number 3000

### 5.1.1 Go To Security Groups

![Screenshot 2026-04-22 180828.png](/Images/Screenshot_2026-04-22_180828.png)

### 5.1.2 Edit Inbound Rules

![image.png](/Images/image%206.png)

### 5.1.3 Add Rule → Type : Custom TCP → Portn Range : 3000 → Source : Anywhere-IPv4 → Save Rules

![image.png](/Images/image%207.png)

## 5.2 Hit It On Browser And Put File Name

`54.161.38.170:3000`

![image.png](/Images/image%208.png)

# 6. Summary

Node Application Is A Monolithic Web Application Developed Using Node.js, Where The Built-In Node Server Handles Both Frontend And Backend Without Requiring Web Servers Like Nginx Or Apache HTTP Server. The Application Is Deployed On A Single AWS EC2 Instance And Uses PM2 To Run And Manage The App In The Background.

It Enables Users To Access The Application Through A Web Browser Using Port 3000 And Demonstrates Basic Full-Stack Development And Deployment In A Monolithic Architecture.
