# 📦 Installing Software via PrivacySafe OS PPAs

PrivacySafe maintains three official package repositories (PPAs) that deliver secure, privacy-focused software for PrivacySafe OS systems. These PPAs can be used whether you're running PrivacySafe OS from downloaded media or preinstalled on hardware such as the Launchpad Pro tablet.

- **Enterprise Release** (stable builds): 
  [https://launchpad.net/~privacysafe/+archive/ubuntu/enterprise-release](https://launchpad.net/~privacysafe/+archive/ubuntu/enterprise-release)

- **Enterprise Testing** (pre-release QA builds): 
  [https://launchpad.net/~privacysafe/+archive/ubuntu/enterprise-testing](https://launchpad.net/~privacysafe/+archive/ubuntu/enterprise-testing)

- **Enterprise Nightly** (automated development builds): 
  [https://launchpad.net/~privacysafe/+archive/ubuntu/enterprise-nightly](https://launchpad.net/~privacysafe/+archive/ubuntu/enterprise-nightly)

PrivacySafe OS is available in two supported editions. The instructions below are organized based on how you acquired your system.

---

## 💻 PrivacySafe OS on Purchased Devices (based on Ubuntu 24.04 LTS)

If you purchased a PrivacySafe hardware device, such as the [Launchpad Pro tablet](https://ivycyber.com/shop), it is running a version of PrivacySafe OS based on **Ubuntu 24.04 LTS**. Follow the steps below to add and manage PrivacySafe PPAs.

**Note:** These instructions also apply to any system running Ubuntu 24.04 LTS.

### 1. Install required tools

```bash
sudo apt update
sudo apt install software-properties-common -y
```

### 2. Add the PrivacySafe PPA

To add the stable release PPA:

```bash
sudo add-apt-repository ppa:privacysafe/enterprise-release
sudo apt update
```

You may substitute `enterprise-release` with:

* `enterprise-testing` for QA builds
* `enterprise-nightly` for latest development versions

### 3. Install PrivacySafe software

```bash
sudo apt install privacysafe-suite
```

---

## 📀 PrivacySafe OS 25.09 Installer (based on Debian 12 Bookworm)

If you downloaded the **PrivacySafe OS 25.09 installer (.iso)**, your system is based on **Debian 12 Bookworm**. Follow the instructions below to manually add PrivacySafe PPAs.

**Note:** These instructions also apply to any system running Debian 12 Bookworm.

### 1. Install required tools

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install software-properties-common gnupg wget -y
```

### 2. Manually add the PrivacySafe PPA

PrivacySafe software is published for Ubuntu 24.04 LTS (codename: `noble`) and is generally compatible with Debian 12.

```bash
echo "deb http://ppa.launchpad.net/privacysafe/enterprise-release/ubuntu noble main" | sudo tee /etc/apt/sources.list.d/privacysafe-release.list
```

### 3. Add the GPG key

```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 2E12848899B2F463409B95A82C83959AD748331E
```

> 🔑 This is the official GPG key used to sign PrivacySafe packages. Confirm the key on the [PrivacySafe PPA website](https://launchpad.net/~privacysafe) if needed.

### 4. Update and install

```bash
sudo apt update
sudo apt install privacysafe-suite
```

---

## 🗑 Removing a PrivacySafe PPA

### On PrivacySafe OS for devices (Ubuntu-based)

```bash
sudo add-apt-repository --remove ppa:privacysafe/enterprise-release
sudo apt update
```

### On PrivacySafe OS 25.09 (Debian-based)

```bash
sudo rm /etc/apt/sources.list.d/privacysafe-release.list
sudo apt-key del 2E12848899B2F463409B95A82C83959AD748331E
sudo apt update
```

---

## ⚠ Important Notes

* Software installed via PrivacySafe PPAs is officially supported **only** on PrivacySafe OS based on Ubuntu 24.04 LTS **when purchased with hardware and a support plan** from [Ivy Cyber](https://ivycyber.com). Contact `orders@ivycyber.com` for details about support plans.

* Ivy Cyber will make best efforts to respond to support requests sent to `support@ivycyber.com` but may refer users to community resources such as GitHub, Ask Ubuntu, and others.

* PrivacySafe OS 25.09 (Debian-based) is community-supported only and not covered by official Ivy Cyber support.

* We maintain a public Matrix channel for questions at
  [https://app.element.io/#/room/#privacysafe\:private.coffee](https://app.element.io/#/room/#privacysafe:private.coffee)

* You may also contact us via:

  * **PrivacySafe Chat**: user `support@privacysafe.me` (requires PrivacySafe Enterprise Chat app)
  * **PrivacySafe Social**: [@privacysafe-support](https://privacysafe.social/@privacysafe-support)
  * Please remember these channels are **public**, so do not share sensitive information.

* If you have an enterprise support plan from Ivy Cyber, you will be provided with private, encrypted support channels. For access or assistance, email `orders@ivycyber.com`. For secure communication, our PGP key is: [2A31 B66D 9359 5A36 423C 7120 376C 7159 AF52 635C](https://keys.openpgp.org/search?q=orders@ivycyber.com)

* Using these PrivacySafe PPAs on other GNU/Linux distributions, or on versions of Ubuntu or Debian other than those specified, may result in errors or dependency conflicts.

* The nightly and testing channels are intended for testing and include unfinished and unstable features. They are not recommended for production or high-risk systems.

* **Always verify** packages before using them in sensitive or production environments. Ivy Cyber and PrivacySafe project contributors are not responsible or liable for damages resulting from improper installation or use and poor operational security. See our [Terms & Conditions](https://ivycyber.com/terms) for full legal details.

## 👥 Visit the PrivacySafe PPA team:
👉 [https://launchpad.net/~privacysafe](https://launchpad.net/~privacysafe)

