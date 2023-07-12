# Hello there!
This documentation is on how to crack a WPS/WPA2 encrypted wifi password using Flipper Zero WiFi-Devemopment board.

Alright let's get started!

# Table of Contents:
- [Hello there!](#hello-there)
- [Table of Contents:](#table-of-contents)
- [Install the prerequisites](#install-the-prerequisites)
  - [Install the Marauder Flash](#install-the-marauder-flash)
  - [Install WireShark](#install-wireshark)
  - [Install Hashcat](#install-hashcat)
  - [Install 7zip](#install-7zip)
  - [Install Python 3.9.6](#install-python-396)
  - [Install the crack passwords](#install-the-crack-passwords)
  - [What I Used: For this tutorial](#what-i-used-for-this-tutorial)
- [Execution](#execution)
  - [Step 0:](#step-0)
  - [Step 1:](#step-1)
  - [Step 2:](#step-2)
  - [Step 3:](#step-3)
  - [Step 4:](#step-4)
  - [Step 5:](#step-5)
  - [Step 6:](#step-6)
  - [Step 7:](#step-7)
  - [Step 8:](#step-8)
  - [Step 9:](#step-9)
- [Conclusion](#conclusion)





-----------------------------------------

# Install the prerequisites

## Install the Marauder Flash

[This is the link to install the Marauder Flash](https://github.com/SkeletonMan03/FZEasyMarauderFlash)

It's recommended to flash the Marauder Flash to the flipper development using Linux or Mac OS.

 [Windows have an issue for quite sometime, so it's recommened to run on Linux or MacOS](https://github.com/SkeletonMan03/FZEasyMarauderFlash/issues/33)



 ----------------------------------------


## Install WireShark

[Wireshark Download](https://www.wireshark.org/)

## Install Hashcat
[Download the lastest release of it](https://github.com/hashcat/hashcat/tags)


After that use 7zip to extract the file.

Then open the command prompt and type in the following command:

```bash
cd C:\Users\%USERNAME%\Downloads\hashcat-6.2.4
```

This will change the directory to the hashcat folder.


## Install 7zip

[Download 7zip](https://www.7-zip.org/download.html)

## Install Python 3.9.6

[Download Python 3.9.6](https://www.python.org/downloads/release/python-396/)

Install this if you don't have it.

## Install the crack passwords

Huge (74 gig): [This large list of passwords](https://h.acker.is/74gb-wordlist-released-princesspi7-4/)
<br>
Common: [Password list](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt&v=subLBPJ3IxU)
<br>
What I Used: [For this tutorial](https://wpa-sec.stanev.org/dict/cracked.txt.gz&v=subLBPJ3IxU)
----------------------------------------

# Execution

Great! Now that you have installed all the prerequisites, let's get started!

## Step 0:
Navigate to Applications ---> GPIO ---> [ESP32] Wifi Marauder

<video src="Image%20and%20Video/Recording%202023-07-12%20175619.mp4" controls title="Nev"></video>

## Step 1: 

![Run AP](./Image%20and%20Video/Screenshot-20230712-175629.png)

Scan your AP 

## Step 2:

Select the AP you want to Deauth and Sniff

![Alt text](<Image and Video/Screenshot-20230712-181816.png>)


## Step 3:
Find your SSID and remember the number beside it.

![Alt text](<Image and Video/Screenshot 2023-07-12 180501.png>)

## Step 4:

Press on Select and Key in the number beside your SSID. Example: 1

## Step 5:
Before you press on the Deauth button, change your Sniff to raw, to make sure that you can sniff the handshake.


<video src="Image%20and%20Video/RAW%20and%20Deauther.mp4" controls title="Title"></video>

## Step 6:

Get your pcap file from the flipper zero and open it with Wireshark.

SD Card ---> app_data ----> marauder ---> pcap ---> Sniffraw_1.pcap



<video src="Image%20and%20Video/Recording75619.mp4" controls title="Title"></video>

## Step 7:
Go click on the .pcap file and it will open up Wireshark. 

Type on the filter bar: `eapol`

You should have something like this: 
```
key(Message 1 of 4), key(Message 2 of 4),
key(Message 3 of 4) and key(Message 4 of 4)
```

<video src="Image%20and%20Video/Eapol%20works.mp4" controls title="Title"></video>

## Step 8:

[Go to this website and upload your .pcap file](https://hashcat.net/cap2hashcat/)

And download the .hc22000 file.


<video src="Image%20and%20Video/Use%20Hashcat%20website.mp4" controls title="Title"></video>

## Step 9:

Drag the .hc22000 file into the hashcat folder.

AND also the cracked.txt.gz file into the hashcat folder. (Depends on what you want to crack)

(Make sure both of the files are in the same folder)

Open up CMD and CD to the hashcat folder.

After run this command

```bash
hashcat -m 22000 (your .hc22000 file) (your cracked.txt.gz file)
```

Example of the command
``` bash
hashcat -m 22000 112313212.hc22000 cracked.txt.gz
``` 

Your password will be cracked in a few seconds or minutes depending on your computer and the password.


<video src="Image%20and%20Video/Password%20Cracked.mp4" controls title="Title"></video>


# Conclusion

You can use this method to crack any WPA/WPA2 password. But it's not 100% guaranteed that you can crack the password. It depends on the password strength and your computer.

Please do not use this method to crack other people's wifi password. This is for educational purposes only and do it on your own wifi!!!




