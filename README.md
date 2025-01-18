# Network Hacking (wifi)

## Objective
Network Hacking and gaining access to WEP encryption networks and cracking them.

### Skills Learned

- Sniffing on 5Gz and 2.5Gz wireless networks
- aircrack-ng
  

### Tools Used

- Kali Linux.
- VMware Fusion.
- airodump-ng
- aircrack-ng

## Steps for WAP

- Changing the wireless USB mode to monitoring
<img width="411" alt="Pasted Graphic 7" src="https://github.com/user-attachments/assets/331fc412-c14a-43f9-92cd-9d5e0591ece8" />


The mode will be Monitor now
- Sniffing on 5G and 2.4G networks and find the network with the cipher WEP
<img width="414" alt="Pasted Graphic 10" src="https://github.com/user-attachments/assets/aca514ea-b534-4d3c-99b0-7a9fcab4786e" />

- Sniffing packets from the network with the WEP cipher with the specific MAC and channel number and save the results in a file test
<img width="818" alt="Pasted Graphic 11" src="https://github.com/user-attachments/assets/755eab9f-7ff2-4114-91fb-a0df3bc51e90" />

- Wait for the #Data number to move real fast and open a new terminal window and ls to find the ".cap" file.
- Use aircrack-ng to find the Key

![tempImagenRwLlV](https://github.com/user-attachments/assets/193415d8-4f1b-4fdc-987e-601ce5c89dee)


- Copy the key and remove the : and that would be the wifi password.

## Steps for WPA/WPA2

￼
