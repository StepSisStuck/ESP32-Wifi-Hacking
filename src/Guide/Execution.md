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
```key(Message 1 of 4), key(Message 2 of 4), key(Message 3 of 4) and key(Message 4 of 4)```


<video width="600" controls>
  <source src="Image%20and%20Video/Eapol%20works.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

### Step 8:
[Go to this website and upload your `.pcap` file](https://hashcat.net/cap2hashcat/)

And download the `.hc22000` file.

<video width="600" controls>
  <source src="Image%20and%20Video/Use%20Hashcat%20website.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

### Step 9:
Drag the `.hc22000` file into the hashcat folder.

AND also the [`cracked.txt.gz`](command:_github.copilot.openSymbolFromReferences?%5B%22%22%2C%5B%7B%22uri%22%3A%7B%22%24mid%22%3A1%2C%22fsPath%22%3A%22c%3A%5C%5CUsers%5C%5CStanly%5C%5CDownloads%5C%5CESP32-Wifi-Hacking%5C%5Csrc%5C%5CGuide%5C%5CExecution.md%22%2C%22_sep%22%3A1%2C%22external%22%3A%22file%3A%2F%2F%2Fc%253A%2FUsers%2FStanly%2FDownloads%2FESP32-Wifi-Hacking%2Fsrc%2FGuide%2FExecution.md%22%2C%22path%22%3A%22%2FC%3A%2FUsers%2FStanly%2FDownloads%2FESP32-Wifi-Hacking%2Fsrc%2FGuide%2FExecution.md%22%2C%22scheme%22%3A%22file%22%7D%2C%22pos%22%3A%7B%22line%22%3A63%2C%22character%22%3A14%7D%7D%5D%5D "Go to definition") file into the hashcat folder (depends on what you want to crack).

Make sure both files are in the same folder.

Open up CMD and CD to the hashcat folder.

Afterward, run this command:

```bash
hashcat -m 22000 (your .hc22000 file) (your cracked.txt.gz file)
```
Your password will be cracked in a few seconds or minutes depending on your computer and the password.

<video width="600" controls> <source src="Image%20and%20Video/Password%20Cracked.mp4" type="video/mp4"> Your browser does not support the video tag. </video> ```