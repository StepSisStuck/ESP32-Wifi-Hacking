# Execution Phase

Great! Now that you have installed all the prerequisites, let's get started!

### Step 0:
Navigate to Applications -> GPIO -> [ESP32] Wifi Marauder

![Run AP](./Image%20and%20Video/Screenshot-20230712-175629.png)

<video width="600" controls>
  <source src="Image%20and%20Video/Recording%202023-07-12%20175619.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

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

<video width="600" controls>
  <source src="Image%20and%20Video/RAW%20and%20Deauther.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

### Step 6:
Get your pcap file from the Flipper Zero and open it with Wireshark.

SD Card -> app_data -> marauder -> pcap -> Sniffraw_1.pcap

<video width="600" controls>
  <source src="Image%20and%20Video/Recording75619.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

### Step 7:
Go click on the `.pcap` file and it will open up Wireshark.

Type on the filter bar: `eapol`

You should have something like this:
