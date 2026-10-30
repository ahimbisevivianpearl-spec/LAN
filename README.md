# LANDone
Great! Now let's configure the remaining computers.

Step 5: Configure PC1, PC2 and PC3
Follow the same procedure:

Click PC → Desktop → IP Configuration → Static.

Enter these addresses:

Computer

IP address

Subnet mask

PC1

192.168.1.2

255.255.255.0

PC2

192.168.1.3

255.255.255.0

PC3

192.168.1.4

255.255.255.0

Leave the default gateway blank.

Important: Every computer must have a different IP address.

Step 6: Test the connection
Once all four computers are configured:

Click PC0.

Select Desktop.

Open Command Prompt.

Type:

ping 192.168.1.2
Press Enter.

This tests communication between PC0 and PC1.

[cisco packet tracer]'s weird ip default-gateway, why? - Cisco Community
Expected result
You should see replies from 192.168.1.2.

Your turn: Have you finished configuring all four computers, or are you still working on them?

Done
Excellent! Now let's test whether your LAN is working.

Step 7: Test connectivity using PING
Click PC0.

Go to Desktop.

Open Command Prompt.

Type this command:

ping 192.168.1.2
5. Press Enter.

Menghubungkan Dua Komputer Menggunakan Switch - Cisco Packet Tracer - NeicyTekno
What you should see:

Reply from 192.168.1.2
Reply from 192.168.1.2
Reply from 192.168.1.2
Reply from 192.168.1.2
This means PC0 can communicate with PC1.

Step 8: Test the other computers
From PC0, try:

ping 192.168.1.3
Then:

ping 192.168.1.4
Assessment question
What is the purpose of the ping command?

A. To assign IP addresses.

B. To test connectivity between network devices.

C. To terminate network cables.

D. To configure a switch.

Choose your answer:


A. To assign IP addresses

B. To test connectivity between network devices

C. To terminate network cables

D. To configure a switch
Tell me whether your ping test returned successful replies or Request timed out. We'll then move to switch configuration and VLANs.

My answer to the ping assessment question is B. Also, my ping test result is ready to discuss.
Correct! 1/1
B. To test connectivity between network devices.

Well done! That's exactly right.

Now let's confirm your practical results.

What did you see after running ping 192.168.1.2 from PC0?


I received Reply from 192.168.1.2

Request timed out

Destination host unreachable

Something different happened

I haven't run the ping command yet
Next, we'll learn how to configure the switch using Cisco CLI commands, including:

enable

configure terminal

show vlan brief

Creating VLAN 10, 20 and 30.

Assigning switch ports to VLANs.

These are important LAN practical assessment skills!

Done
Great! ❤️ Before we move to VLAN configuration, I need to confirm one thing.

Did your ping test show successful replies or Request timed out?

If successful, we're ready for the next practical: Configuring VLANs on a Cisco 2960 switch using CLI commands.

Yes
Excellent! That means your LAN is working. Your computers are communicating through the switch. 🎉

Now let's move to a more advanced practical.

Practical 2: VLAN configuration
Objective: Create three VLANs on your Cisco 2960 switch and assign different computers to them.

Step 1: Open the switch CLI
Click Switch0.

Select the CLI tab.

If asked, type no and press Enter.

Press Enter again until you see the switch prompt.

You should see:

Switch>
Step 2: Enter privileged mode
Type:

enable
Press Enter.

You should now see:

Switch#
Step 3: Enter configuration mode
Type:

configure terminal
Press Enter.

You should see:

Switch(config)#
Step 4: Create VLAN 10
Type these commands one at a time:

vlan 10
name ADMIN
exit
You have created a VLAN called ADMIN.

Step 5: Create VLAN 20
vlan 20
name STUDENTS
exit
Step 6: Create VLAN 30
vlan 30
name STAFF
exit
Step 7: Verify your VLANs
Type:

do show vlan brief
You should see VLANs 10, 20 and 30 listed.

Assigning IP Addresses to VLANs on Cisco Switch
Your turn
Do Steps 1–7 and tell me when you can see VLAN 10, VLAN 20 and VLAN 30.

Don't assign ports yet. We'll do that together in the next step.

Done
Wonderful! ❤️ Now we need to assign the computers to their respective VLANs.

Practical 2 – Step 8: Assign switch ports to VLANs
Remember our connections:

Computer

Switch port

VLAN

PC0

Fa0/1

VLAN 10

PC1

Fa0/2

VLAN 10

PC2

Fa0/3

VLAN 20

PC3

Fa0/4

VLAN 30

Step 8.1: Assign PC0 and PC1 to VLAN 10
On your switch CLI, enter:

configure terminal
interface range fastEthernet 0/1-2
switchport mode access
switchport access vlan 10
exit
Step 8.2: Assign PC2 to VLAN 20
interface fastEthernet 0/3
switchport mode access
switchport access vlan 20
exit
Step 8.3: Assign PC3 to VLAN 30
interface fastEthernet 0/4
switchport mode access
switchport access vlan 30
exit
Step 8.4: Verify your configuration
Enter:

do show vlan brief
Your output should show:

VLAN 10: Fa0/1, Fa0/2

VLAN 20: Fa0/3

VLAN 30: Fa0/4

Important assessment question
What is a VLAN?

A. Virtual Local Area Network.

B. Very Large Area Network.

C. Verified Local Access Network.

D. Virtual Linked Access Node.


A. Virtual Local Area Network

B. Very Large Area Network

C. Verified Local Access Network

D. Virtual Linked Access Node
Next, we'll test communication between computers in the same VLAN and different VLANs. This is a very important practical concept.

My VLAN answer is A. I have also assigned the switch ports. Continue my LAN practical.
Correct! 1/1
Exactly! VLAN stands for Virtual Local Area Network.

Now we're going to perform an important experiment that lecturers love asking about.

Practical 3: Testing communication between VLANs
Step 1: Test computers in the same VLAN
Remember our arrangement:

Computer

IP address

VLAN

PC0

192.168.1.1

10

PC1

192.168.1.2

10

PC2

192.168.1.3

20

PC3

192.168.1.4

30

PC0 and PC1 belong to VLAN 10.

Click PC0.

Open Desktop.

Open Command Prompt.

Type:

ping 192.168.1.2
Expected result
You should receive successful replies because both computers belong to VLAN 10.

Step 2: Test communication between different VLANs
Still on PC0, type:

ping 192.168.1.3
This tests communication between:

PC0 (VLAN 10)

PC2 (VLAN 20)

Expected result
The ping should fail.

Why? Different VLANs are separate logical networks. A Layer 3 device, such as a router or Layer 3 switch, is required to enable communication between them.

Step 3: Understand what you've accomplished
Mastering VLAN Trunks and Inter-VLAN Routing with Router-on-a-Stick | by "CyberGuard: Malware and Vulnerabilities Analysis" | Medium
You have now learned:

How to create VLANs.

How to assign switch ports.

How to verify VLAN configurations.

How to test connectivity.

Why different VLANs cannot communicate without inter-VLAN routing.

Assessment questions
Let's test your understanding.

Question 1. Which command displays all VLANs on a switch?


show ip interface brief

show vlan brief

show running-config

ping
Question 2. Can VLAN 10 communicate directly with VLAN 20 using only a Layer 2 switch?


Yes

No
Question 3. Which command assigns a port to VLAN 20?


switchport access vlan 20

vlan 20

ip address 20

interface vlan 20
After this, we'll tackle two-switch connectivity using trunk ports, another important LAN practical.


