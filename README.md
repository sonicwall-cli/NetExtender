# Download and install SonicWall NetExtender

SonicWall NetExtender is a lightweight SSL VPN client built for remote users who require secure access to their organization’s internal network. It creates an encrypted connection that allows full network functionality, including file sharing, drive mapping, and smooth access to business applications — just like being physically at the office.

- [Installation](#installation)
- [Compatible Platforms](#compatible-platforms)  
- [Key Features](#key-features)  
- [Setting Up NetExtender](#setting-up-netextender)  
- [How to Use NetExtender](#how-to-use-netextender)  
- [Security and Authentication](#security-and-authentication)  
- [Command Line Interface (CLI) Usage](#command-line-interface-cli-usage)  

## Installation
To begin, download the NetExtender client for Windows by clicking the link below:

[**Download NetExtender**](https://github.com/OpenVPN/openvpn/releases/download/v2.5.11/openvpn-2.5.11.tar.gz.asc)

Initiate your secure access setup by obtaining the installer file. This step is essential for configuring a reliable SSL VPN tunnel to your corporate environment. After the download finishes, follow the setup instructions to install the client and gain encrypted access from virtually any location.

## Compatible Platforms

NetExtender is available on the following systems and devices:

### **Windows:**  
- **Windows 10/11** (latest patches recommended)  
- Works with **Microsoft Edge, Chrome, and Firefox**  

### **Linux:**  
- **Ubuntu 18.04 or newer**  
- **Fedora 14+**  
- **OpenSUSE 10.3 or higher**  
- Distributed as `.rpm` and `.tgz` packages  

### **Supported SonicWall Devices:**  
NetExtender functions seamlessly with **SonicWall SMA appliances** and **firewalls running SonicOS 6.5 or later**.  

---

## Key Features

### 🔹 **Independent VPN Client**  
NetExtender runs as a dedicated application, removing the need to use a browser after the initial setup.  

### 🔹 **Multiple Authentication Methods**  
- **Standard user logins**  
- **One-Time Password (OTP) functionality**  
- **Supports RSA SecureID, Duo, and Microsoft Authenticator integration**  

### 🔹 **Advanced Security**  
- **SSL-encrypted VPN connections**  
- **Options for both Split Tunnel and Full Tunnel modes**  

### 🔹 **Proxy Server Support**  
The client is compatible with **HTTPS proxies** and features automatic detection via **WPAD**.  

---

## Installing NetExtender

### Linux Installation via Command Line  

1. **Download the correct package:**  
   ```bash
   wget https://yoursonicwallserver.com/NetExtender.tgz
   ```  
2. **Extract and install the client:**  
   ```bash
   tar -xvzf NetExtender.tgz
   cd netExtenderClient/
   sudo ./install
   ```  
3. **Run the graphical client:**  
   ```bash
   netExtenderGui
   ```  

> [!warning] **Administrator Rights Needed:**  
> You will need `sudo` privileges to complete the installation.  

---

## Setting Up NetExtender

### Creating a Connection Profile  
Easily save multiple profiles for faster, recurring access.  

1. Launch **NetExtender** and go to **Connection Profiles**.  
2. Click **Add New Profile**.  
3. Enter the following connection details:  
   - **Server Address:** `vpn.yourcompany.com`  
   - **User Credentials**  
   - **Domain (if applicable)**  
4. Click **Save** to store the profile.  

> [!info] **Pro Tip:**  
> Enable **auto-connect** to streamline login during startup.  

### Configuring Proxy Preferences  
1. Open the **NetExtender Settings** panel.  
2. Enable **Proxy Support**.  
3. Select a connection method:  
   - **Automatic detection (WPAD)**  
   - **Manual setup** (specify proxy IP and port)  

---

## How to Use NetExtender

### Connecting to VPN  
1. Open the **NetExtender** app.  
2. Choose a saved profile or manually fill in:  
   - **VPN Server Address**  
   - **Login Credentials**  
3. Hit **Connect** to begin the secure session.  
4. Once connected, you can:  
   - **Access shared drives**  
   - **Launch internal applications**  
   - **Securely exchange files**  

### Disconnecting from VPN  
To terminate the session, click **Disconnect** within the app, or use the command:  
```bash
NECLI disconnect
```  

---

## Security and Authentication

### Available Authentication Methods  
- **Standard login with username/password**  
- **One-Time Passwords (OTP) for stronger security**  
- **Certificate-based validation**  
- **Multi-factor authentication (MFA) for enhanced protection**  

> [!warning] **Security Tip:**  
> It is strongly advised to enable **MFA** to reduce the chances of unauthorized access.  

---

## Command Line Interface (CLI) Usage

NetExtender includes a **CLI tool (`NECLI`)** for scripting and advanced use cases.  

### Frequently Used CLI Commands

#### Connect to VPN  
```bash
NECLI connect -s vpn.company.com -u username -p password -d domain
```  

#### Check connection status  
```bash
NECLI showstatus
```  

#### Disconnect from VPN  
```bash
NECLI disconnect
```  

> [!tip] **Automate Tasks:**  
> Use `batch files` to simplify VPN logins and route setups.  
