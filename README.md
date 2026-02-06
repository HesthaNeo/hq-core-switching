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
            <p>- For this next step, we will configure HSRP under all VLAN interfaces to share an IP address between the switches to provide first-hop gateway redundancy, ensuring uninterrupted network connectivity if a primary switch were to fail. This will create a virtual IP and MAC address shared between the switches, allowing hosts to maintain a consistent default gateway IP, thereby minimizing downtime during network failures.</p>
                <img width="866" height="761" alt="Screenshot 2026-02-05 185513" src="https://github.com/user-attachments/assets/7286b27b-ce25-455d-996d-57ad053ce965" />
                <img width="867" height="797" alt="Screenshot 2026-02-05 185911" src="https://github.com/user-attachments/assets/c42797f9-9c5d-4a12-ae2c-0885ffd90a3d" />
            <p><em>- For the priority 255 command, it will force the switch to be the primary gateway, while configuring priority 0 will ensure it is the last resort for the specific vlan. The preempt command allows the higher priority switch to immediately seize control from the active switch with lower the priority if there happened to be a device failure.</em></p>
        <h3>Step 8: Configure Spanning-Tree VLAN Priority</h3>
            <p>- Next we'll configure spanning-tree vlan priority to split the role of the primary root bridge between the core switches. This will affect traffic from access layer switches coming back to the core, so that we may optimize traffic flow, balancing the load across redundant paths, and ensure predictable, stable topology behavior.</p>
               <img width="867" height="622" alt="Screenshot 2026-02-05 191451" src="https://github.com/user-attachments/assets/396acc9b-f7b1-47c9-b86a-28779aff0949" />
               <img width="873" height="632" alt="Screenshot 2026-02-05 191659" src="https://github.com/user-attachments/assets/15aa2f05-3911-4f7a-8f45-e53785a02188" />
        <h3>Step 9: Configure Trunk Ports</h3>
            <p>- Now we will connect a 2nd ethernet cross-over cable connecting both G0/2 ports on the switches, and we will configure the two gigabit ethernet connections we have currently as aggregated trunk links. We do this to combine both physical links into a single logical interface, preventing a single point of failure and while also optimizing throughput without having to upgrade our hardware. We will then configure these as a trunk to allow for multiple VLANs to pass through the aggregated link.</p>
                <img width="1983" height="1013" alt="Screenshot 2026-02-05 192700" src="https://github.com/user-attachments/assets/f9ee4465-0203-424c-a218-498f13517fc4" />
                <img width="1437" height="1510" alt="Screenshot 2026-02-05 193047" src="https://github.com/user-attachments/assets/fc1ece7a-9aa9-4dfa-b67e-a92c9445e58f" />
                <img width="869" height="1500" alt="Screenshot 2026-02-05 193821" src="https://github.com/user-attachments/assets/d5aa3d81-6925-4056-92dd-1373ce03a9f4" />
                <img width="866" height="383" alt="Screenshot 2026-02-05 194141" src="https://github.com/user-attachments/assets/4dfe7f6e-f926-4653-b409-1cd9bc6fa76c" />
            <p><em>- We implement the "switchport trunk encapsulation dot1q" command to ensure the switch adds VLAN tags to the frames, allowing multiple VLANs to traverse the single link while we maintain separation. Lastly, we use the "channel-group 1 mode on" command to immediately create a "static" (forced) etherchannel/aggregated link, which is why we were seeing those status updates frequently during that process.</em></p>
            <p>- Now we will configure the trunk ports for the fast ethernet ports Fa0/19 - 24 on each switch.</p>
                <img width="868" height="151" alt="Screenshot 2026-02-05 200013" src="https://github.com/user-attachments/assets/85f3feb4-cae2-4ec8-a2e3-465dd9078e63" />
                <img width="868" height="151" alt="Screenshot 2026-02-05 200013" src="https://github.com/user-attachments/assets/6c4af609-f41d-4dcb-a3b7-15713dd7195a" />
        <h3>Step 10: Configure Access Ports</h3>
            <p>- Now we will configure all necessary access ports so that the corresponding end devices may connect to their specific vlan. We do this to provide security by segregating the traffic, simplifying network management, and ensuring these end devices only receive data intended for their assigned network segment. We will be configuring fast access ports Fa0/1 - 18 for both switches. </p>
                <img width="1052" height="409" alt="Screenshot 2026-02-05 201205" src="https://github.com/user-attachments/assets/c12a924d-9722-48a2-9370-d7b6c153fe52" />
                <img width="1047" height="455" alt="Screenshot 2026-02-05 201305" src="https://github.com/user-attachments/assets/624861d2-f3f3-4e81-ac94-b26b86432d69" />
                <img width="870" height="449" alt="Screenshot 2026-02-05 201517" src="https://github.com/user-attachments/assets/cba4bc98-edab-464e-bd36-508502afb0bf" />
                <img width="866" height="416" alt="Screenshot 2026-02-05 201605" src="https://github.com/user-attachments/assets/dded2016-33c2-4fa9-910f-0a59057cc025" />
            <p><em>- We implement the "spanning-tree portfast" command to allow the accessport to transition immediately to the forwarding state, skipping the 30-50 second delay of listening and learning states. This is so end-user devices can receive instant network access, but while still running spanning-tree on the switch itself to prevent loops. Lastly, we use the "mls qos trust device cisco-phone" command on these specific access ports if a device identifies itself via cisco discovery drotocol (CDP) as a cisco IP phone, we're telling the switch to trust the voice quality markings it sends and prioritize its traffic. </em></p>
        <h3>Step 11: Configure Static Routes</h3>
            <p>- Now we will configure a default route to point to the HQ internet router data interface IP address (Not installed yet). Next we will ensure we have a route to Branch 1 and Branch 2 networks pointing to the HQ WAN router data IP interface. Lastly, we will ensure we have a route to the private WAN service provider network, pointing to the HQ WAN router data interface IP address. (Both Switches)</p>
                <img width="861" height="433" alt="Screenshot 2026-02-05 204143" src="https://github.com/user-attachments/assets/728eed5c-ceba-4812-97fd-6dcb35ca2dd6" />
                <img width="868" height="336" alt="Screenshot 2026-02-05 204710" src="https://github.com/user-attachments/assets/4988b0aa-73d0-4cfd-a791-3773d6bb62c0" />
        <h3>Step 12: Verify Connectivity In The Network</h3>
             <p>- For the final step in this first milestone, we will now connect a network operations PC to the MGMT VLAN for management of the network and verification purposes.</p>
             <p>- A. We will drag and drop a PC into the topology and label it as "NOC-PC".</p>
                 <img width="759" height="879" alt="Screenshot 2026-02-06 150935" src="https://github.com/user-attachments/assets/0a07c603-27f1-4fa0-b91f-aa2b937cf2ea" />
             <p>- B. Next we will connect a straight-through cable from PC FastEthernet0 to an access port on HQ-CORE-SW1.</p>
                 <img width="736" height="860" alt="Screenshot 2026-02-06 151141" src="https://github.com/user-attachments/assets/ab1a2448-ffc5-41f0-8a56-6ded3b8fa10c" />
             <p>- C. Next we will configure that same cccess port on HQ-CORE-SW1 (fa0/1) for switchport access vlan 100, our MGMT vlan.</p>
                 <img width="872" height="291" alt="Screenshot 2026-02-06 151443" src="https://github.com/user-attachments/assets/101c922d-7e40-4c25-8685-7a9ab83f8cec" />
             <p>- D. Now we'll click on the PC to configure a static IP address, subnet mask, and default gateway. Our IP address for this NOC PC will be 192.168.110.50 255.255.255.0 with a default gateway of 192.168.110.100.</p>
                 <img width="866" height="885" alt="Screenshot 2026-02-06 151929" src="https://github.com/user-attachments/assets/7e648545-ee3b-499e-a5a4-336bfd5a2bf6" />
                 <img width="872" height="886" alt="Screenshot 2026-02-06 152003" src="https://github.com/user-attachments/assets/f4aed5d9-e0a3-4e91-8214-ea609b6830c1" />



            












 





