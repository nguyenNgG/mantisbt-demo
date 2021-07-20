# Prerequisites

This is a simplified list of requirements for MantisBT.
A more comprehensive and detailed document could be found at the [official MantisBT Admin Guide](https://mantisbt.org/docs/master/en-US/Admin_Guide/html-desktop/#admin.install.requirements).
Generally, this guide aims for a hassle-free and minimal installation process.

---

## 1. Software Requirements

### 1.1. MariaDB Database

The preferred database to use for MantisBT is MySQL, or one of its forks, such as MariaDB. For this guide, we will be using MariaDB just because it's open-source.

### 1.2. XAMPP Web Server Package

XAMPP is a free web server package developed by Apache Friends. As XAMPP makes it trivial to setup a PHP web server, this will be what we will use for this guide.

---

## 2. Installing the Required Software

### 2.1. MariaDB Database

1. For the scope of this guide, it's best to download MariaDB at the [MariaDB Downloads Page](https://downloads.mariadb.org/). Any stable version should be fine, this guide will be using version 10.5.10. The MSI Package Type will be chosen to ensure an easy installation process.

2. With regards to the objective of this guide, we will only install a few components included in the installation package:

- MariaDB Server: Database Instance - For creating a new database
- (Optional) Third party tools: HeidiSQL - A user-friendly UI for database management if you want to verify the database initialized by MantisBT.

If you choose to install HeidiSQL, be sure to create an user credential for accessing the database.

### 2.2. XAMPP Web Server Package

1. Similar to MariaDB, we will also be downloading XAMPP from [the XAMPP Download Page](https://www.apachefriends.org/download.html). XAMPP for Windows + PHP 8.0.7 is chosen for this guide. It should be noted that PHP is included in the XAMPP installation package.

2. As we seek only the bare minimum, the only components to be installed are:

- Server: Apache
- Program Languages: PHP

### 2.3. MantisBT

1. Needless to say, we'll need to download MantisBT to set it up. Head over to the [MantisBT Download Page](https://www.mantisbt.org/download.php) and download the lastest version. Version 2.25.2 is chosen for this guide.

2. Once the download finished, extract the archive, there should be a folder and a .tar.gz file. The .tar.gz is for Linux and could be safely deleted.

3. Optionally, rename the folder to "mantisbt". This folder name will be put in the url when you access MantisBT.

## 3. Server Setup

1. If you had installed HeidiSQL, you could use it to access the MariaDB server and verify its installation status. Otherwise, skip to step 2.

2. Navigate to the installation folder of XAMPP, find the executable xampp-control.exe, open its Properties and enable 'Run this program as Administrator' in Compatibility. After that, run the executable and start Apache Server. Wait for the server to start then stop it.

3. Navigate to the htdocs folder, put the MantisBT folder extracted from the downloaded archive inside.

4. Start Apache Server, open your browser, access the below url.

```md
<your_server>/<your_mantis>/admin/install.php
```

5. Fill in the required information for the installation.

Make sure Admin Username and Admin Password is filled in.

6. Press 'Install/Upgrade Database' to begin the installation process.

7. Wait for the installation to complete, might take a while depending on your machine.

8. Verify that the installation is complete.

---

## Next steps

Continue to post installation document to continue the setting up MantisBT.
