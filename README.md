<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>
<h1><u>Milestone 2: HQ Core-Switching</u></h1>
    <p>First phase, we will install 2 Cisco WS-C3560-24PS configured with port-channel, Hot Standby Router
Protocol, Per VLAN Spanning-Tree (PVST) with dual root and split VLAN traffic, and VTP Server.</p>
    <h2><strong><u>Configuration Steps</u></strong></h2>
        <h3>Step 1: Rack mount, power on and cable both switches</h3>
            <p>- First, we open Control Panel, go to Programs and Features, and click Turn Windows Features on or off. From there we scroll down to find IIS, and enable it.</p>
                <img src="https://i.imgur.com/1auhZ9x.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- The next thing was to expand the IIS section, find Application Development Features, and enable the CGI as well.</p>
                <img src="https://i.imgur.com/TMm3m0Q.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
        <h3>Step 2: Install Web Platform Installer</h3>
            <p>- In this step, we will install the Web Platform Installer. To do that, we must first download and install the PHP Manager for IIS.</p>
                <img src="https://i.imgur.com/dvRGYh4.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/zcVEfvA.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Next, was to download and install the rewrite module.</p>
                <img src="https://i.imgur.com/IHmjB4G.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/cvy9y6B.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/B05X8xj.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>\
            <p>- After installing the rewrite module, we needed to create the directory C:\PHP, in order to install the PHP zip file that we were required to download.</p>
                <img src="https://i.imgur.com/e30wr5m.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/tFEJ4f6.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
        <h3>Step 3: Install C++ Redistributable</h3>
            <p>- Next is to install the C++ Redistributable file for the installation.</p>
                <img src="https://i.imgur.com/JudjfNP.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/k1BomJx.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/9QXJKrT.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
        <h3>Step 4: Install MySQL and Setup Username and Password</h3>
            <p>- For this step, we will install my SQL for our database server management.</p>
                <img src="https://i.imgur.com/4htBXSF.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- We used Typical Setup for this installation.</p>
                <img src="https://i.imgur.com/1kipAj6.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/HHgDG3I.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- After the installation, we make sure to launch the Configuration Wizard.</p>
                <img src="https://i.imgur.com/G6BUp9i.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Use the Standard Configuration and install.</p>
                <img src="https://i.imgur.com/0ZrRzsS.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/H6G2VHy.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
        <h3>Step 5: Configure Permissions and Install osTicket</h3>
            <p>- In this step, in order to configure the permissions and install osTicket, we begin by opening IIS as an admin. After doing that, we register PHP from within IIS.</p>
                <img src="https://i.imgur.com/twEf0iH.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Registering PHP in IIS. (Restart the Server)</p>
                <img src="https://i.imgur.com/jXujTa2.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/zXI8GbD.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Next was to install osTicket that we downloaded previously and to extract the upload folder to c:\inetpub\wwwroot. (Restart the Server)</p>
                <img src="https://i.imgur.com/2gevzDj.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Next, in IIS, we go to Sites, Default, osTicket. On the right side, we click "Browse *:50 (http)"</p>
                <img src="https://i.imgur.com/3asSOdu.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/vAB8JuZ.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Since some of the extensions were still not enabled, we went back to IIS and clicked on Sites, Default, osTicket. From there we clicked on PHP Manager where we clicked Enable or disable extension.</p>
                <img src="https://i.imgur.com/YlnyHAk.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- We made sure to enable php_imap.dll, php_intl.dll, and php_opcache.dll.</p>
                <img src="https://i.imgur.com/15NESF5.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- After refreshing the osTicket site in the browser, we can see that the extensions we selected were enabled.</p>
                <img src="https://i.imgur.com/iggkGzO.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Next was to rename the configuration file for PHP from: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, to: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
                <img src="https://i.imgur.com/hKieodf.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/T6PmTIf.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- We assigned permissions for ost-config.php, which included Disable Inheritance, and then adding New Permissions to Everyone with All permissions.</p>
                <img src="https://i.imgur.com/sap6H01.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/2FbBBGM.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- From there, we can continue to setting up osTicket in our web browser.</p>
                <img src="https://i.imgur.com/9OfbfQa.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- In order to continue with the setup of osTicket, we need to download and install Heidi SQL.</p>
                <img src="https://i.imgur.com/xnBs3zY.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/geTitRw.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- After installation, we created a new session, connected to the session, and inside Heidi SQL, created a database called "osTicket".</p>
                <img src="https://i.imgur.com/R6EMCMO.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/KSOupuY.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Once completed, we head back to our web browser to continue setting up osTicket with the apppropriate credentials.</p>
                <img src="https://i.imgur.com/eC8KngO.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- After this, we can click install now, and osTicket has been successfully installed. We can browse to our osTicket help desk login page, and see our fully functioning ticketing system.</p>
                <img src="https://i.imgur.com/vekCFPR.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <img src="https://i.imgur.com/sa23Bwi.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>    <p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>
<h1><u>osTicket - Prerequisites and Installation</u></h1>
    <p>This lab demonstration outlines the prerequisites and installation of the open-source help desk ticketing system, osTicket.</p>
    <h2><em>Environments and Technologies Used</em></h2>
        <ul>
            <li>Microsoft Azure (Virtual Machines/Compute)</li>
            <li>Remote Desktop</li>
            <li>Internet Information Services (IIS)</li>
        </ul>
    <h2><em>Operating Systems Used</em></h2>
        <ul>
            <li>Windows 10 (21H2)</li>
        </ul>
    <h2><em>List of Prerequisites</em></h2>
        <ul>
            <li>Enable Internet Information Services (IIS) with CGI (Common Gateway Interface)</li>
            <li>Install Web Platform Installer</li>
            <li>Install C++ Redistributable</li>
            <li>Install MySQL and Setup Username and Password</li>
            <li>Configure Permissions and Install osTicket</li>
        </ul>
    <h2><strong><u>Installation Steps</u></strong></h2>
        <h3>Step 1: Enable Internet Information Services (IIS) with CGI (Common Gateway Interface)</h3>
            <p>- First, we open Control Panel, go to Programs and Features, and click Turn Windows Features on or off. From there we scroll down to find IIS, and enable it.</p>
                <img src="https://i.imgur.com/1auhZ9x.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- The next thing was to expand the IIS section, find Application Development Features, and enable the CGI as well.</p>
                <img src="https://i.imgur.com/TMm3m0Q.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
        <h3>Step 2: Install Web Platform Installer</h3>
            <p>- In this step, we will install the Web Platform Installer. To do that, we must first download and install the PHP Manager for IIS.</p>
                <img src="https://i.imgur.com/dvRGYh4.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/zcVEfvA.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Next, was to download and install the rewrite module.</p>
                <img src="https://i.imgur.com/IHmjB4G.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/cvy9y6B.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/B05X8xj.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>\
            <p>- After installing the rewrite module, we needed to create the directory C:\PHP, in order to install the PHP zip file that we were required to download.</p>
                <img src="https://i.imgur.com/e30wr5m.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/tFEJ4f6.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
        <h3>Step 3: Install C++ Redistributable</h3>
            <p>- Next is to install the C++ Redistributable file for the installation.</p>
                <img src="https://i.imgur.com/JudjfNP.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/k1BomJx.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/9QXJKrT.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
        <h3>Step 4: Install MySQL and Setup Username and Password</h3>
            <p>- For this step, we will install my SQL for our database server management.</p>
                <img src="https://i.imgur.com/4htBXSF.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- We used Typical Setup for this installation.</p>
                <img src="https://i.imgur.com/1kipAj6.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/HHgDG3I.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- After the installation, we make sure to launch the Configuration Wizard.</p>
                <img src="https://i.imgur.com/G6BUp9i.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Use the Standard Configuration and install.</p>
                <img src="https://i.imgur.com/0ZrRzsS.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/H6G2VHy.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
        <h3>Step 5: Configure Permissions and Install osTicket</h3>
            <p>- In this step, in order to configure the permissions and install osTicket, we begin by opening IIS as an admin. After doing that, we register PHP from within IIS.</p>
                <img src="https://i.imgur.com/twEf0iH.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Registering PHP in IIS. (Restart the Server)</p>
                <img src="https://i.imgur.com/jXujTa2.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/zXI8GbD.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Next was to install osTicket that we downloaded previously and to extract the upload folder to c:\inetpub\wwwroot. (Restart the Server)</p>
                <img src="https://i.imgur.com/2gevzDj.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Next, in IIS, we go to Sites, Default, osTicket. On the right side, we click "Browse *:50 (http)"</p>
                <img src="https://i.imgur.com/3asSOdu.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/vAB8JuZ.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Since some of the extensions were still not enabled, we went back to IIS and clicked on Sites, Default, osTicket. From there we clicked on PHP Manager where we clicked Enable or disable extension.</p>
                <img src="https://i.imgur.com/YlnyHAk.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- We made sure to enable php_imap.dll, php_intl.dll, and php_opcache.dll.</p>
                <img src="https://i.imgur.com/15NESF5.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- After refreshing the osTicket site in the browser, we can see that the extensions we selected were enabled.</p>
                <img src="https://i.imgur.com/iggkGzO.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Next was to rename the configuration file for PHP from: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php, to: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
                <img src="https://i.imgur.com/hKieodf.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/T6PmTIf.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- We assigned permissions for ost-config.php, which included Disable Inheritance, and then adding New Permissions to Everyone with All permissions.</p>
                <img src="https://i.imgur.com/sap6H01.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/2FbBBGM.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- From there, we can continue to setting up osTicket in our web browser.</p>
                <img src="https://i.imgur.com/9OfbfQa.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- In order to continue with the setup of osTicket, we need to download and install Heidi SQL.</p>
                <img src="https://i.imgur.com/xnBs3zY.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/geTitRw.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- After installation, we created a new session, connected to the session, and inside Heidi SQL, created a database called "osTicket".</p>
                <img src="https://i.imgur.com/R6EMCMO.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
                <img src="https://i.imgur.com/KSOupuY.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- Once completed, we head back to our web browser to continue setting up osTicket with the apppropriate credentials.</p>
                <img src="https://i.imgur.com/eC8KngO.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <p>- After this, we can click install now, and osTicket has been successfully installed. We can browse to our osTicket help desk login page, and see our fully functioning ticketing system.</p>
                <img src="https://i.imgur.com/vekCFPR.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
            <img src="https://i.imgur.com/sa23Bwi.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>    
