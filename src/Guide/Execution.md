# Execution Phase

Great! Now that you have installed all the prerequisites, let's get started!

### Step 0:
Navigate to Applications -> GPIO -> [ESP32] Wifi Marauder

![Run AP](./Image%20and%20Video/Screenshot-20230712-175629.png)

[![Watch the video](Image%20and%20Video/Recording%202023-07-12%20175619.mp4)](Image%20and%20Video/Recording%202023-07-12%20175619.mp4)

### Step 1:
Scan your AP

### Step 2:
Select the AP you want to Deauth and Sniff

![Alt text](Image%20and%20Video/Screenshot-20230712-181816.png)

### Step 3:
Find your SSID and remember the number beside it.

![Alt text](Image%20and%20Video/Screenshot%202023-07-12%20180501.png)

### Step 4:
Press on Select and Key in the number beside your SSID. Example: 1

### Step 5:
Before you press on the Deauth button, change your Sniff to raw to make sure that you can sniff the handshake.

[![Watch the video](Image%20and%20Video/RAW%20and%20Deauther.mp4)](Image%20and%20Video/RAW%20and%20Deauther.mp4)

### Step 6:
Get your pcap file from the Flipper Zero and open it with Wireshark.

SD Card -> app_data -> marauder -> pcap -> Sniffraw_1.pcap

[![Watch the video](Image%20and%20Video/Recording75619.mp4)](Image%20and%20Video/Recording75619.mp4)

### Step 7:
Go click on the `.pcap` file and it will open up Wireshark.

Type on the filter bar: `eapol`

You should have something like this:

```
key(Message 1 of 4), key(Message 2 of 4),
key(Message 3 of 4) and key(Message 4 of 4)
```

[![Watch the video](Image%20and%20Video/Eapol%20works.mp4)](Image%20and%20Video/Eapol%20works.mp4)

### Step 8:
[Go to this website and upload your `.pcap` file](https://hashcat.net/cap2hashcat/)

And download the `.hc22000` file.

[![Watch the video](Image%20and%20Video/Use%20Hashcat%20website.mp4)](Image%20and%20Video/Use%20Hashcat%20website.mp4)

### Step 9:
Drag the `.hc22000` file into the hashcat folder.

AND also the `cracked.txt.gz` file into the hashcat folder (depends on what you want to crack).

Make sure both files are in the same folder.

Open up CMD and CD to the hashcat folder.

Afterward, run this command:

```bash
hashcat -m 22000 (your .hc22000 file) (your cracked.txt.gz file)
```

Example of the command:

```bash
hashcat -m 22000 112313212.hc22000 cracked.txt.gz
```

Your password will be cracked in a few seconds or minutes depending on your computer and the password.

[![Watch the video](Image%20and%20Video/Password%20Cracked.mp4)](Image%20and%20Video/Password%20Cracked.mp4)