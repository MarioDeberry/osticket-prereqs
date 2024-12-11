<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket Setup Guide - Prerequisites and Installation

This guide provides step-by-step instructions for installing the osTicket helpdesk system on a Windows server. It covers setting up required environments, installing dependencies, and configuring the system to be fully operational.

---

## Technologies and Platforms

- **Microsoft Azure** (Virtual Machines/Compute)
- **Remote Desktop Connection**
- **Internet Information Services (IIS)**

## Supported Operating Systems

- **Windows 10** (21H2)

---

## Prerequisites

Before starting the installation, make sure the following components are installed and configured:

- **IIS** with the Management Console
- **PHP** and the **PHP Rewrite Module**
- **MySQL** Database
- **HeidiSQL** for MySQL Management
- **osTicket System Files**

---

## Step-by-Step Installation Guide

### 1. Create and Set Up a Virtual Machine
- Follow this guide on how to create a virtual machine on **Microsoft Azure**: [Creating Virtual Machines](https://github.com/MarioDeberry/Configuring-Active-Directory-within-Azure-VMs).
- Install **Windows 10** and connect using **Remote Desktop**.

### 2. Install IIS and Dependencies
1. Right-click on the Start menu and select **Run**.
2. Type `control panel`, press Enter.
3. Go to **Programs** > **Turn Windows Features On or Off**.
4. Enable **Internet Information Services (IIS)** and ensure **CGI** is also enabled under **World Wide Web Services** > **Application Development Features**.
5. Install **PHP Manager** and the **URL Rewrite Module**.

#### Screenshot:
![IIS Installation](https://i.imgur.com/fFI8SvZ.png)

---------------------------------------------------                                                  

![IIS Installation](https://i.imgur.com/JNTSgtY.png)

---

### 3. Install PHP and MySQL
1. Create a directory called `C:\PHP`.
2. Download **PHP** and unzip the files into the `C:\PHP` folder.
3. Install the **VC Redist** (x86 version) and **MySQL** (use the Typical Setup option).
4. Open the **MySQL Configuration Wizard**, select **Standard Configuration**, and create a username and password. Keep these credentials safe for later.

#### Screenshot:
![PHP and MySQL Setup](https://i.imgur.com/Q3lFtDX.png)


------------------------------------------------------

![PHP and MySQL Setup](https://i.imgur.com/GvNVFNT.png)
---

### 4. Register PHP with IIS and Install osTicket
1. Open **IIS Manager** as Administrator.
2. Register the **PHP** installation in IIS by navigating to the **PHP Manager**.
3. Stop and restart the IIS server for changes to take effect.
4. Download the **osTicket system files**, extract them, and move the **uploads** folder to `C:\inetpub\wwwroot\osTicket`.
5. Rename the **ost-sampleconfig.php** file to **ost-config.php** in the `C:\inetpub\wwwroot\osTicket\include` directory.

#### Screenshot:
![osTicket Setup](https://i.imgur.com/YHCknRJ.png)

----------
![osTicket Setup](https://i.imgur.com/hny3ScG.png)

---

### 5. Enable PHP Extensions and Configure Permissions
1. In **IIS**, go to **Sites** > **Default** > **osTicket**.
2. Double-click **PHP Manager**, then click on **Enable or Disable an Extension**.
3. Enable the following extensions:
   - **php_imap.dll**
   - **php_intl.dll**
   - **php_opcache.dll**
4. Set file permissions for the `ost-config.php` file to **"Read, Read and Execute"** for **Everyone**.

#### Screenshot:
![PHP Extension Configuration](https://i.imgur.com/5AIrTsc.png)

---

### 6. Set Up the Database Using HeidiSQL
1. Download and install **HeidiSQL**.
2. Open HeidiSQL and create a new session to connect to the MySQL server.
3. Create a new database named **osTicket**.
4. Complete the osTicket installation form with your MySQL credentials and database details.

### 7. Complete Installation
1. Click **Install Now** and follow the remaining setup steps.
2. After installation, navigate to your helpdesk login page at localhost/osTicket/scp/login.php
3. For security, delete the `setup` folder from `C:\inetpub\wwwroot\osTicket`.
4. Update file permissions for `ost-config.php` to restrict access.

---

## Conclusion

You have successfully installed osTicket. From here, you can:
- **Explore osTicket functionalities** for managing and resolving support tickets.
- **Learn administrative features** such as account setup and ticket prioritization.

<h2>  <img src="https://raw.githubusercontent.com/ShahriarShafin/ShahriarShafin/main/Assets/handshake.gif" width="100"> </h2>

---

### Troubleshooting Tips:
- **PHP Extensions**: If the system fails to load correctly, double-check that the required PHP extensions are enabled.
- **Database Issues**: Ensure MySQL is running and that the correct database name and credentials are entered during the osTicket setup.


---


---
