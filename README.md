<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket Logo"/>
</p>

<h1 align="center">How to Install osTicket</h1>
<p align="center">
  This guide provides an easy-to-follow process for installing the osTicket help desk ticketing system.
</p>

---

## 📂 Files You Need to Download
- [Download Required Files](https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

---

## 🛠️ Software & Technologies Used
- **Windows 10** (21 H2)
- **Microsoft Azure** (Virtual Machines)
- **Remote Desktop Protocol (RDP)**
- **Internet Information Services (IIS)**

---

## 📋 Prerequisites
Before starting the installation, make sure the following components are installed and configured:

- **IIS** with the Management Console
- **PHP** and the **PHP Rewrite Module**
- **MySQL** Database
- **HeidiSQL** for MySQL Management
- **osTicket System Files**

---

## 🚀 Steps to Install osTicket

### 1. Create a Virtual Machine in Azure
1. Open **Azure** and create a **Resource Group**.
   - You can name it "osTicket" for this tutorial.
    <p align="center">
     <img src="https://i.imgur.com/lp8bbY2.png" width="80%">
   </p>

3. Create a **Windows 10 Virtual Machine (VM)** with 2-4 vCPUs.
   - Set a username and password for remote login.
   - Allow Azure to create a new Virtual Network (Vnet).

   <p align="center">
     <img src="https://imgur.com/7BZDj3r.png" width="80%">
   </p>

4. Use the **Remote Desktop Connection** app on your computer to connect to the VM.
   - Use the public IP address of the virtual machine created within Azure.
   <p align="center">
     <img src="https://github.com/Joeljjoseph1998/osticket-prereqs/assets/50834280/2e71fd86-4198-47aa-aa1a-d0aed1b8e0eb" alt="RDP Connection" width="80%">
   </p>

---

### 2. Enable Internet Information Services (IIS)
1. Open **Control Panel** → **Programs** → **Turn Windows features on or off**.
2. Enable **Internet Information Services (IIS)**:
   - Expand **World Wide Web Services** → **Application Development Features**.
   - Check the box for **CGI**.

   <p align="center">
     <img src="https://imgur.com/UMSyyeX.png" alt="Enable IIS" width="80%">
   </p>

---

### 3. Install PHP Manager and Rewrite Module
1. Download and install the **PHP Manager**.
   <p align="center">
     <img src="https://imgur.com/Xtqs9TI.png" alt="Install PHP Manager" width="80%">
   </p>

2. Install the **Rewrite Module**.
   <p align="center">
     <img src="https://github.com/Joeljjoseph1998/osticket-prereqs/assets/50834280/28cf2dd0-d39e-45f8-a01b-61aec6657228" alt="Install Rewrite Module" width="80%">
   </p>

---

### 4. Configure PHP
1. Create a directory at `C:\PHP`.
2. Download `php-7.3.8-nts-Win32-VC15-x86.zip` from the [Required Files](https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).
3. Extract the contents into the `C:\PHP` folder.
   <p align="center">
     <img src="https://imgur.com/PJxs0TW.png" alt="Configure PHP" width="80%">
   </p>

---
### 5. VC_REDIST DOWNLOAD</h3>
1. <h3 align="center"> Download and install VC_Redist, Agree with any terms and agreements and finish installing.

<p align="center">
     <img src="https://imgur.com/T2JkZ89.png" width="80%">

---
### 6. Install MySQL
1. Download and install **MySQL**.
2. Select "Standard Configuration" 
3. Set a username and password (e.g., `root` and `root`) for database management.
<p align="center">
     <img src="https://imgur.com/W0CovQJ.png" width="80%">

   <p align="center">
     <img src="https://imgur.com/2MhHPzU.png" width="80%">
   </p>

---

### 7. Install osTicket
1. Download osTicket and extract the `upload` folder to `C:\inetpub\wwwroot`.
2. Rename the folder to `osTicket`.
   <p align="center">
     <img src="https://i.imgur.com/pDikkgq.png" alt="osTicket Setup" width="80%">
   </p>

3. Open IIS Manager:
   - Go to **Sites → Default → osTicket**.
   - On the right-hand menu, click **Browse *:80**.
     <p align="center">
       <img src="https://i.imgur.com/3iXhNbi.png" alt="Browse osTicket" width="80%">
     </p>

---
### 8. Enable Extensions in IIS
1. Go back to IIS, `Sites` `Default` `osTicket`
   - Double-click PHP Manager:
   - Click “Enable or disable an extension”.
</p>
<p>
	Enable: php_imap.dll.
</p>
<p>
	Enable: php_intl.dll.
</p>
<p>
	Enable: php_opcache.dll:
</p>
<p>
	<img src="https://imgur.com/y2ZQfV2.png" height="75%" width="100%"/>


---
### 9. Configure osTicket
1. Rename `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php` to `ost-config.php` in the `include` directory.
2. Assign permissions to the `ost-config.php` file.
3. Disable inheritance - Remove All
4. New Permissions - Everyone All

<p align="center">
     <img src="https://imgur.com/6JOTO5k.png" width="80%">

 <p align="center">
     <img src="https://imgur.com/xWAm2yE.png" alt="Cleanup" width="80%">
   </p>
   <p align="center">
     <img src="https://imgur.com/8mpTs8w.png" alt="Cleanup" width="80%">
   </p>
   <p align="center">
     <img src="https://imgur.com/U5g0234.png" alt="Cleanup" width="80%">
     

### 10. Final Steps
 Continue setup in your osTicket browser:
   - Set up database details (MySQL).
   - Open Heidi SQL and Create a new database called "osTicket", name the username and password root/root
   - Click **Install Now!**
   - Name your helpdesk and provide a default email.
   

   <p align="center">
     <img src="https://imgur.com/6L5vxjG.png" width="80%">
   </p>


---

## 🎉 Congratulations!
You have successfully installed osTicket. From here, you can:
- **Explore osTicket functionalities** for managing and resolving support tickets.
- **Learn administrative features** such as account setup and ticket prioritization.

<h2>  <img src="https://raw.githubusercontent.com/ShahriarShafin/ShahriarShafin/main/Assets/handshake.gif" width="100"> </h2>

<p align="center">
  <img src="https://imgur.com/cINdm8R.png" alt="osTicket Admin Panel.png" width="80%">
</p>
