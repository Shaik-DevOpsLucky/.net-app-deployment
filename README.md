# Deploying a .NET (Static Website) on AWS Windows Server using IIS

This guide explains how to host a simple .NET/HTML website on an **AWS EC2 Windows Server** using **IIS Web Server**.

---

## 🔐 Login Details (Example)
**User:** Administrator  
**Password:** *<your-windows-password>*

> ⚠️ Do NOT store real passwords in documentation. Use placeholders only.

---

## 📌 Prerequisites
- An AWS account  
- A Windows EC2 instance launched  
- RDP client to connect to the server  
- Security Group with **Port 80 (HTTP)** open  

Reference:  
https://k21academy.com/aws-cloud/aws-ec2-instance/

---

## 🚀 Step 1: Launch and Log in to Windows EC2 Instance
1. Launch an EC2 Windows Server from AWS Console.  
2. Download RDP file and decrypt the Administrator password.  
3. Login using RDP.

---

## 🛠️ Step 2: Install IIS Web Server
1. Open **Server Manager**  
2. Click **Add Roles and Features**  
3. Click **Next → Next**  
4. Under **Server Roles**, select:  
   - **Web Server (IIS)**  
5. Click **Add Features**  
6. Click **Next → Next → Install**  
7. Wait until installation completes.

After installation, IIS creates a new folder in:
```
C:\inetpub\wwwroot
```

---

## 🌐 Step 3: Allow HTTP (Port 80) in Security Group
In AWS:
1. Go to **EC2 → Security Groups**  
2. Edit Inbound Rules  
3. Add:  
   - **Type:** HTTP  
   - **Port:** 80  
   - **Source:** 0.0.0.0/0  

This allows public access to your webpage.

---

## 📥 Step 4: Download a Free Template on the Windows Server
1. Open **Chrome/Edge** inside the EC2 Windows Server  
2. Download any free HTML/CSS template:  
   https://templatemo.com/page/35  
3. Extract the downloaded ZIP file.

---

## 📂 Step 5: Replace the IIS Default Files
1. Open the extracted template folder  
2. Copy all files and folders  
3. Go to:
```
C:\inetpub\wwwroot
```
4. Delete the existing IIS default files  
5. Paste your template files

Your application is now ready to serve.

---

## 🌍 Step 6: Access the Application
Open any browser and access:

```
http://<your-ec2-public-ip>/
```

Example:
```
http://3.236.242.210/
```

---

## ✅ Done!
Your .NET/HTML static app is now successfully hosted on AWS Windows Server using IIS.
