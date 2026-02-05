<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>
<h1><u>Milestone 2: HQ Core-Switching</u></h1>
    <p>First phase, we will install 2 Cisco WS-C3560-24PS configured with port-channel, Hot Standby Router
Protocol, Per VLAN Spanning-Tree (PVST) with dual root and split VLAN traffic, and VTP Server.</p>
    <h2><strong><u>Configuration Steps</u></strong></h2>
        <h3>Step 1: Rack Mount, Power On and Cable Both Switches</h3>
            <p>- First, we'll add two 3560 switches to the topology by dragging and dropping them into the Headquarters 
section of the lab. Place them side by side and label them as HQ-CORE-SW1 & HQ-CORE-SW2.</p>
                <img width="1978" height="1039" alt="Screenshot 2026-02-05 173646" src="https://github.com/user-attachments/assets/bef0dc50-1028-4d73-85a9-3f554476c6da" />
        <h3>Step 2: Basic Switch Configurations (Hostname, NTP, Domain-Name, SSH, Etc)</h3>
            <p>- In this step, we did basic configuration for both of the switches including changing their hostnames, setting their time zones, enabling SSH, setting domain names, adding securiting to console and vty lines for SSH, and creating user profiles with a password the devices.</p>
                <img width="925" height="1042" alt="Screenshot 2026-02-05 174601" src="https://github.com/user-attachments/assets/b41860bc-2ea6-450d-a5c5-0f99b8e24ed3" />
                <img width="869" height="922" alt="Screenshot 2026-02-05 175059" src="https://github.com/user-attachments/assets/aeb08dd4-b957-44c0-b626-f9de45faa802" />
        <h3>Step 3: Enable IP Routing</h3>
            <p>- Next is to enable IP Routing and multilayer switch quality of service to allow communication between different VLANs (subnets) directly on the switch and so that critical traffic gets priority.</p>
                <img width="870" height="884" alt="Screenshot 2026-02-05 175900" src="https://github.com/user-attachments/assets/51785ecf-fd6c-4980-bf86-3986d609e2c9" />
                <img width="866" height="886" alt="Screenshot 2026-02-05 175948" src="https://github.com/user-attachments/assets/c9caab27-d06c-4fc6-afc6-2c6d1fbad001" />
        <h3>Step 4: Create VLANs (10, 100, 172, & 192)</h3>
            <p>- For this step, we will now create these VLANs on both switches to segment a single physical network infrastructure into multiple, isolated, logical networks, improving performance, security, and management.</p>
                <img width="869" height="920" alt="Screenshot 2026-02-05 180818" src="https://github.com/user-attachments/assets/9bf9ce07-cc81-4e64-ad62-6f9865424ea9" />
                <img width="870" height="884" alt="Screenshot 2026-02-05 181021" src="https://github.com/user-attachments/assets/c47cb564-3475-49e1-8b9e-a03253684591" />
        <h3>Step 5: Configure VLAN Trunking Protocol (VTP) Server</h3>
            <p>- In this step, we will configure the VLAN Trunking Protocol Server to centralize and automate the management of VLAN configurations (add, delete, rename) across all switches in this topology.</p>
                <img width="869" height="956" alt="Screenshot 2026-02-05 181801" src="https://github.com/user-attachments/assets/fafc602d-5167-46e5-978a-5a821b52ddab" />
                <img width="868" height="954" alt="Screenshot 2026-02-05 182024" src="https://github.com/user-attachments/assets/5d99222e-830f-4727-a75b-4fa69ab05f5b" />
        <h3>Step 6: Create VLAN Interfaces</h3>
            <p>- For this step, we will create the VLAN interfaces for the corresponding VLANs we have created, so that we can in fact route traffic between the different VLANs, enabling inter-VLAN communication.</p>
                <img width="866" height="744" alt="Screenshot 2026-02-05 183818" src="https://github.com/user-attachments/assets/163ad1d5-f493-45e2-8456-a2ea8ab5bd31" />
                <img width="867" height="729" alt="Screenshot 2026-02-05 183940" src="https://github.com/user-attachments/assets/644f4b1e-93ef-44ef-8cc7-b691a4c8ffe8" />
        <h3>Step 7: Configure HSRP For All VLAN Interfaces</h3>



