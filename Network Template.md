# Network Analysis

## Time Thieves
At least two users on the network have been wasting time on YouTube. Usually, IT wouldn't pay much mind to this behavior, but it seems these people have created their own web server on the corporate network. So far, Security knows the following about these time thieves:
- They have set up an Active Directory network.
- They are constantly watching videos on YouTube.
- Their IP addresses are somewhere in the range 10.6.12.0/24.

You must inspect your traffic capture to answer the following questions:

- What is the domain name of the users' custom site?
  - The domain name for the users' custom site is frank-n-ted.com
- What is the IP address of the Domain Controller (DC) of the AD network?
  - The IP address of the DC is 10.6.12.12.
- What is the name of the malware downloaded to the 10.6.12.203 machine? Once you have found the file, export it to your Kali machine's desktop.
  - The name of the malware downloaded to the 10.6.12.203 machine is june11.dll.
- Upload the file to VirusTotal.com. What kind of malware is this classified as?
  - The malware is classified as a Trojan. 
 
 
## Vulnerable Windows Machines
The Security team received reports of an infected Windows host on the network. They know the following:
- Machines in the network live in the range 172.16.4.0/24.
- The domain mind-hammer.net is associated with the infected computer.
- The DC for this network lives at 172.16.4.4 and is named Mind-Hammer-DC.
- The network has standard gateway and broadcast addresses.
- Inspect your traffic to answer the following questions:

### Find the following information about the infected Windows machine:
- Host name: Rotterdam-PC.mind-hammer.net
- IP address: 172.16.4.205
- MAC address: 00:59:07:b0:63:a4

- What is the username of the Windows user whose computer is infected?
  - The username of the infected computer is Matthijs Devries.
- What are the IP addresses used in the actual infection traffic?
  - The IP addresses used int eh infecteion traffic are 166.62.11.64 and 185.243.115.84.
As a bonus, retrieve the desktop background of the Windows host.

## Illegal Downloads
IT was informed that some users are torrenting on the network. The Security team does not forbid the use of torrents for legitimate purposes, such as downloading operating systems. However, they have a strict policy against copyright infringement.
- IT shared the following about the torrent activity:
- The machines using torrents live in the range 10.0.0.0/24 and are clients of an AD domain.
- The DC of this domain lives at 10.0.0.2 and is named DogOfTheYear-DC.
- The DC is associated with the domain dogoftheyear.net.
- Your task is to isolate torrent traffic and answer the following questions:

### Find the following information about the machine with IP address 10.0.0.201:
  - MAC address: 00:16:17:18:66:c8
  - Windows username: Elmer Blanco
  - OS version: Windows NT 10.0 x64

Which torrent file did the user download?
- Betty_Boop_on_the_reservation.avi.torrent
