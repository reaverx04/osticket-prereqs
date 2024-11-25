<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro </b> Version 21H2, at least 2vCPUs, 8GB RAM

<h2>List of Prerequisites</h2>

- IIS and Management Console
- PHP and Rewrite Module
- MySQL
- HeidiSQL
- osTicket

<h2>Installation Steps</h2>

<p>
Open your <strong>osticket-vm</strong> and download <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD"><strong>osTicket-Installation-Files.zip</strong></a> to the desktop. After downloading, right-click the file and choose <strong>Extract All</strong> to create the <strong>osTicket-Installation-Files</strong> folder. Open the folder to ensure all installation files are there.  
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
Open <strong>Control Panel</strong> > <strong>Programs</strong> > <strong>Turn Windows features on or off</strong>. In the <strong>Windows Features</strong> window, expand <strong>Internet Information Services</strong>, check <strong>World Wide Web Services</strong>, and under <strong>Application Development Features</strong>, check <strong>CGI</strong>. Click <strong>OK</strong> to apply the changes.
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Install **PHP Manager for IIS** (PHPManagerForIIS_V1.5.0.msi) and the **Rewrite Module** (rewrite_amd64_en-US.msi) from the **osTicket-Installation-Files** folder.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Create the **C:\PHP** directory and unzip **php-7.3.8-nts-Win32-VC15-x86.zip** from the **osTicket-Installation-Files** folder into it.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Install **VC_redist.x86.exe** and **MySQL 5.5.62** from the **osTicket-Installation-Files** folder.

Choose **Typical Setup**, then launch the **Configuration Wizard** after installation. Select **Standard Configuration**, and set the **Username** to **root** and the **Password** to **root**.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Open IIS as an admin. In **PHP Manager**, register PHP by selecting **C:\PHP\php-cgi.exe**. Then, reload IIS by stopping and starting the server.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Install **osTicket v1.15.8** by unzipping **osTicket-v1.15.8.zip** from the **osTicket-Installation-Files** folder. Copy the **upload** folder to **c:\inetpub\wwwroot** and rename it to **osTicket**.

Finally, reload IIS by stopping and starting the server.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Some extensions may not be enabled.

- Go to **IIS** > **Sites** > **Default** > **osTicket**.
- Double-click **PHP Manager**.
- Click **Enable or disable an extension**.
    - Enable **php_imap.dll**.
    - Enable **php_intl.dll**.
    - Enable **php_opcache.dll**.
- Refresh the **osTicket** site in your browser to observe the changes.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Rename **ost-sampleconfig.php** to **ost-config.php**

- From: **C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php**
- To: **C:\inetpub\wwwroot\osTicket\include\ost-config.php**

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Assign permissions to **ost-config.php**:

- Right-click **ost-config.php** and select **Properties**.
- Go to the **Security** tab.
- Click **Advanced**, then **Disable inheritance** and select **Remove all inherited permissions**.
- Add new permissions: Select **Everyone** and grant **Full control** (All permissions).

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Continue setting up **osTicket** in your browser by clicking **Continue**.

For **Helpdesk Settings**, enter a **Helpdesk Name** and set the **Default Email** (the email address that will receive messages from customers).

In the **Database Settings** section, you'll need to install **HeidiSQL** from the **osTicket-Installation-Files** folder.

Once **HeidiSQL** is installed, open the program and create a new session with the **Username** set to `root` and the **Password** set to `root`. After connecting to the session, create a new database called **osTicket**.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


Continue setting up **osTicket** in the browser:

- For **MySQL Database**, enter `osTicket`.
- For **MySQL Username**, enter `root`.
- For **MySQL Password**, enter `root`.
- Click **Install Now!** to complete the installation.

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Congratulations! Hopefully, the installation was successful with no errors!

- To log in as an **admin**, go to:
    
    http://localhost/osTicket/scp/login.php
    
- For the **general user** view, visit:
    
    http://localhost/osTicket/
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
text
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
text
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
text
</p>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
