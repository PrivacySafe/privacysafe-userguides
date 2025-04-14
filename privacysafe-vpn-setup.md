# 🛡️PrivacySafe VPN Setup

Welcome to PrivacySafe! Our software deliver privacy and security while you communicate, collaborate, and work. This guide walks you through setting up [PrivacySafe VPN](https://privacysafe.app), covering both OpenVPN and Wireguard connections. Using this guide, you will be able to use your credentials to configure your VPN connections on Windows, Mac, GNU/Linux, iPhone iOS, Android, and even on Ethernet routers and WiFi access points. Follow the relevant instructions for your operating system or device.

You can use PrivacySafe VPN alongside our [Enterprise Suite](https://github.com/PrivacySafe/privacysafe-userguides) and free web apps. Let's get started! ✨

## 📚 Table of Contents
1. [**Desktop or Laptop with OpenVPN**](#openvpn-setup)
   - [Windows Setup (OpenVPN)](#windows-setup-openvpn)
   - [Mac Setup (OpenVPN)](#mac-setup-openvpn)
   - [GNU/Linux Setup (OpenVPN)](#gnulinux-setup-openvpn)
2. [**Desktop or Laptop with Wireguard**](#wireguard-setup)
   - [Windows Setup (Wireguard)](#windows-setup-wireguard)
   - [Mac Setup (Wireguard)](#mac-setup-wireguard)
   - [GNU/Linux Setup (Wireguard)](#gnulinux-setup-wireguard)
3. [**Smartphone Setup (OpenVPN & Wireguard)**](#smartphone-setup-openvpn-wireguard)
   - [iPhone iOS Setup](#iphone-ios-setup)
   - [Android Setup](#android-setup)
4. [**Router Setup (OpenVPN & Wireguard)**](#router-setup-openvpn-wireguard)
   - [GL.iNet GL-A1300 Pocket VPN Travel Router](#glinet-gl-a1300-pocket-vpn-travel-router-setup)
5. [**Troubleshooting**](#troubleshooting)
   - [**Technical Notes**](#technical-notes)
        - [Server Fingerprints](#server-fingerprints)
        - [Regenerating Client & Server Keys (OpenVPN)](#regenerating-client-server-keys-openvpn)
        - [Adding Clients to the OpenVPN Server](#adding-clients-to-the-openvpn-server)

## 💻 Desktop or Laptop with OpenVPN

Your PrivacySafe OpenVPN instance is hosted on a server that will be provided by our PrivacySafe team. You will need the **OpenVPN client configuration** file, which contains your credentials and will be provided to you separately.

### Windows Setup (OpenVPN)

1. **Download and Install OpenVPN:**
 - Go to the [OpenVPN downloads page](https://openvpn.net/index.php/open-source/downloads.html) and download the latest version for Windows.
 - Run the installer and follow the installation steps.

2. **Install Configuration Files:**
 - Place the provided VPN client configuration file in the OpenVPN configuration folder (`C:\Program Files\OpenVPN\config`).

3. **Launch OpenVPN GUI:**
 - Open **OpenVPN GUI** (you can find it in the Start menu).
 - Right-click the OpenVPN icon in your system tray and select **Connect**. It will use the configuration file to initiate the connection.

4. **Verify the Connection:**
 - After connecting, verify the connection by checking your IP address at [psafe.ly/myip](https://psafe.ly/myip). If the IP matches the VPN server's IP, you are connected.

**NOTE:**
- If the server's ed25519 fingerprint is required during setup or verification, please refer to the information provided to you by our PrivacySafe team.

### Mac Setup (OpenVPN)

1. **Download and Install OpenVPN:**
 - Download the official OpenVPN client for MacOS from [OpenVPN's website](https://openvpn.net/index.php/open-source/downloads.html).
 - Install it by following the on-screen instructions.

2. **Install Configuration Files:**
 - Open the **OpenVPN GUI** and import the provided client configuration file.

3. **Start the VPN Connection:**
 - Launch **Tunnelblick** (the OpenVPN client for MacOS).
 - Click on the Tunnelblick icon in the top menu bar and select **Connect**.

4. **Verify the VPN Connection:**
 - After connecting, verify your IP at [psafe.ly/myip](https://psafe.ly/myip) to confirm your connection to the VPN server.

### GNU/Linux Setup (OpenVPN)
These instructions are for Debian-based distributions such as Ubuntu.

1. **Install OpenVPN:**
 - Install the OpenVPN client using the following command:
 ```bash
 sudo apt install openvpn
 ```

2. **Install Configuration Files:**
 - Place the provided **client configuration** file in the OpenVPN configuration directory:
 ```bash
 sudo cp client.ovpn /etc/openvpn/
 ```

3. **Start the VPN Connection:**
 - To connect, run the following command:
 ```bash
 sudo openvpn --config /etc/openvpn/client.ovpn
 ```

4. **Verify the VPN Connection:**
 - After connecting, verify your IP in a web browser at [psafe.ly/myip](https://psafe.ly/myip) to confirm your connection to the VPN server.
 - To verify the connection in the terminal, run:
 ```bash
 curl https://psafe.ly/myip
 ```

## ⚡ Desktop or Laptop with Wireguard

Your PrivacySafe Wireguard VPN is hosted on a server that will be provided by our PrivacySafe team. Follow the steps below for each platform to connect to the Wireguard VPN.

### Windows Setup (Wireguard)

1. **Download and Install Wireguard:**
 - Download and install the **Wireguard client** for Windows from the official [Wireguard website](https://www.wireguard.com/install/).

2. **Install Configuration Files:**
 - Copy the **wg0.conf** file from the VPS server.
 - In the Wireguard client, click **Add Tunnel** and select **Add empty tunnel**.
 - Paste the configuration into the new tunnel file.

3. **Activate the VPN Connection:**
 - After importing the configuration, click **Activate** to establish the connection.

4. **Verify the VPN Connection:**
 - Once the VPN is connected, verify the connection by visiting [psafe.ly/myip](https://psafe.ly/myip). Your public IP should now match the VPN server's IP.  Your should be connected to Iceland in Europe.

### Mac Setup (Wireguard)

1. **Download Wireguard:**
 - Download and install the **Wireguard app** from the [App Store](https://www.wireguard.com/install/).

2. **Import Configuration:**
 - Copy the **wg0.conf** file from the VPS server to your Mac device.
 - Open the Wireguard app, and select **Import tunnel from file**.
 - Choose the **wg0.conf** file you copied.

3. **Start the VPN Connection:**
 - Once the configuration is loaded, you can click **Activate** to connect to the VPN.

4. **Verify the VPN Connection:**
 - Once the VPN is connected, verify the connection by visiting [psafe.ly/myip](https://psafe.ly/myip). Your public IP should now match the VPN server's IP.  Your should be connected to Iceland in Europe.

### GNU/Linux Setup (Wireguard)

1. **Install Wireguard:**
 - On a Debian/Ubuntu-based system, run the following command:
 ```bash
 sudo apt install wireguard
 ```

2. **Install Configuration Files:**
 - Copy the provided **wg0.conf** file from the VPS server to your local machine:
 ```bash
 sudo cp /etc/wireguard/wg0.conf /etc/wireguard/
 ```

3. **Start the VPN Connection:**
 - Run the following command to start the VPN connection:
 ```bash
 sudo wg-quick up wg0
 ```

4. **Verify the VPN Connection:**
 - After connecting, verify your IP in a web browser at [psafe.ly/myip](https://psafe.ly/myip) to confirm your connection to the VPN server.
 - To verify the connection in the terminal, run:

 ```bash
 ip link show wg0
 ```
 - Ensure the **wg0** interface appears.
 - You can test the connection by pinging the server:
 ```bash
 ping 10.10.10.1
 ```

## 📱 Smartphone Setup (OpenVPN &amp; Wireguard)

PrivacySafe VPN works seamlessly using both OpenVPN and Wireguard protocols on iOS and Android. Follow the steps below for each platform.

### iPhone iOS Setup

1. **Install OpenVPN (if using OpenVPN):**
 - Download the **OpenVPN Connect** app from the [App Store](https://apps.apple.com/us/app/openvpn-connect/id590379981).

2. **Install Wireguard (if using Wireguard):**
 - Download the **Wireguard** app from the [App Store](https://apps.apple.com/us/app/wireguard/id1441195209).

3. **Import Configuration:**
 - For **OpenVPN**, import the `.ovpn` configuration file into the OpenVPN app.
 - For **Wireguard**, import the `wg0.conf` file into the Wireguard app.

4. **Activate the VPN:**
 - Open the app and activate the VPN by switching the toggle to **On**.

5. **Verify the VPN Connection:**
 - Once the VPN is connected, verify the connection by visiting [psafe.ly/myip](https://psafe.ly/myip). Your public IP should now match the VPN server's IP.  Your should be connected to Iceland in Europe.

### Android Setup

1. **Install OpenVPN (if using OpenVPN):**
 - Download the **OpenVPN for Android** app from the [Google Play Store](https://play.google.com/store/apps/details?id=net.openvpn.openvpn3).
 - Alternatively, you can also download **OpenVPN for Android** from [F-Droid](https://f-droid.org/en/packages/de.blinkt.openvpn/) which does not require a Google Account.

2. **Install Wireguard (if using Wireguard):**
 - Download the **Wireguard** app from the [Google Play Store](https://play.google.com/store/apps/details?id=com.wireguard.android).
 - Alternatively, you can download **WG Tunnel** from [F-Droid](https://f-droid.org/en/packages/com.zaneschepke.wireguardautotunnel/) which does not require a Google Account.

3. **Import Configuration:**
 - For **OpenVPN**, import the `.ovpn` configuration file into the OpenVPN app.
 - For **Wireguard**, import the `wg0.conf` file into the Wireguard app.

4. **Activate the VPN:**
 - Open the app and activate the VPN by switching the toggle to **On**.

5. **Verify the VPN Connection:**
 - Once the VPN is connected, verify the connection by visiting [psafe.ly/myip](https://psafe.ly/myip). Your public IP should now match the VPN server's IP.  Your should be connected to Iceland in Europe.

## 🌍 Router Setup (OpenVPN &amp; Wireguard)

We recommend using a travel router such as the easy-to-use **GL.iNet VPN Travel Router** models. Alternatively, you can set up your PrivacySafe VPN on a local Ethernet router or WiFi access point, using [DD-WRT](https://dd-wrt.com) or [OpenWRT](https://openwrt.org) if necessary. Setting up PrivacySafe VPN on the physical gateway to your network provides seamless connectivity for all connected devices, without the need for configuring individual operating systems.

### GL.iNet VPN Travel Router

This guide is for the [GL.iNet GL-A1300](https://privacysafe.is/search?q=GL.iNet+GL-A1300) which provides easy VPN setup with our PrivacySafe VPN and supports both OpenVPN and Wireguard. Here's how to set it up:

1. **Log in to the Router Interface:**
 - Connect your computer to the GL-A1300 router via Wi-Fi or Ethernet.
 - Open a web browser and navigate to [http://192.168.8.1](http://192.168.8.1).
 - Log in using the default credentials. These are found on a barcode sticker on the router case.

2. **Set Up OpenVPN:**
 - Navigate to the **VPN** section in the router's settings.
 - Upload the provided **OpenVPN configuration file** to the router's OpenVPN configuration section.
 - Apply the settings and enable the VPN.

3. **Set Up Wireguard:**
 - Navigate to the **Wireguard** settings in the VPN section.
 - Import the **wg0.conf** configuration file provided by the PrivacySafe server.
 - Activate the VPN on your router.

4. **Verify the VPN Connection:**
 - Once the VPN is connected, verify the connection by visiting [psafe.ly/myip](https://psafe.ly/myip). Your public IP should now match the VPN server's IP.  Your should be connected to Iceland in Europe.

## 🛠️ Troubleshooting
 🧐 If you encounter any issues with the PrivacySafe Enterprise Suite, follow these troubleshooting steps:
 - **Step 1**: Check that your internet connection is stable and active.
 - **Step 2**: Ensure that you have followed the instructions for your operating system and device.
 - **Step 3**: If the problem persists, contact our support team.
 - ✉️ Email us directly at **support@privacysafe.net** with:
    - A brief description of the issue
    - The error message (if any)
    - Your operating system and device model
    - Steps to replicate the issue, if applicable

### Technical Notes
These are technical notes for advanced users, and may only apply in cases where you are working directly with PrivacySafe support. Please contact support@privacysafe.net before attempting to generate new fingerprints or credentials.

#### Server Fingerprints
To check the server fingerprint on your system, you can run the following:

- **For OpenVPN**:
```bash
openvpn --config your-vpn-config.ovpn --verify-fingerprint
```

- **For Wireguard**:
Check the fingerprint using:
```bash
wg show
```

#### Regenerating Client & Server Keys (OpenVPN)
- To regenerate the client and server keys, run:
```bash
/usr/local/bin/regenerate-vpn-config.py
```

#### Adding Clients to the OpenVPN Server
- To add additional clients, run:
```bash
/usr/local/bin/add-vpn-client.py
```
- This will generate a new client configuration file.
