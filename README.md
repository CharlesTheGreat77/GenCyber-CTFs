# GenCyber CTF Challenges

![gencyber](https://github.com/CharlesTheGreat77/GenCyber-CTFs/assets/27988707/c24e99db-123d-4cb4-8b39-6175fe19ad12)

# The Messenger
To Solve:
Use https://cyberchef.io
- Base 64 -> Hex -> Text -> ROT13

# Insider
To Solve:
To solve this hard crypto challenge, they need to go to the layerzero github repo specified in the challenge.
Hopefully they notice it is XOR encrypted from dcode.fr or other analytical sources, if not let them know. 
The AMOUNT of projects on the github is the key to decode the message (5). 
use https://cyberchef.io
-> XOR (5 as the key)
OR
They can bruteforce the XOR encryption key with cyberchef using the:
XOR Bruteforce option
FLAG: GC24{mSfR3vYers3_cl4m_4t_IP}


# W2 Tax Document
Theres a file hidden in the jpg file, to extract the hidden text file, use steghide from the commandline
```
steghide extract -sf W2_Documents.jpg 
```
NO PASSWORD, JUST PRESS ENTER
IF NO steghide is on the Kali system, use this:
https://www.aperisolve.com/
This will extract a text file called secret.txt, download the secret.txt file
```
cat secret.txt
```
FLAG: GC24{St3g4n0gr4phy_1s_4ws0m3}

# Cat Island
To Solve:
```
exiftool KIsland.jpg
```
Extract the Author and Copyright fields which is base58
use cyberchef
base58 -> Base64 -> Base64
FLAG: GC24{Ao_Island}


# Twist it, Pull it, String it
To Solve:
```
strings pwn-1
```
depending on the arch, the output will be different for the flag, they will need to solve such to make sure the flag is formatted correctly.
FLAG: GC24{V4rIabl3s_aR3_N0_s3cr3t}


# Evil Twin
To Solve:
You can use aircrack (takes longer)
```
aircrack-ng -w /usr/share/wordlists/rockyou.txt Network-01.cap
```
OR
You can use hashcat (faster)
first go here and upload the Network-01.cap file to this website:
https://hashcat.net/cap2hashcat/
Download the newly generated file that has a file extension of hc22000
```
hashcat -m 22000 -a 0 <NEW_FILE.hc22000> /usr/share/wordlists/rockyou.txt
```
FLAG: cybermaster (I think.. it was one from rockyou.txt with cyber in it so just have patience!)

# Cobalt Strike
To Solve:
Open pcap in wireshark and filter for http traffic
RIGHT-CLICK on one HTTP packet -> Follow HTTP OR TCP Stream -> It's the first ".dll" file in the stream
FLAG: crypted_dll.bin


# AgentTesla V3
To Solve:
Open the .eml file, and they must extract the LONG base64 encoded lines that is in the email to a new text file.
Because the base64 is awfully long, open ```pluma``` in the terminal and open the file and delete EVERYTHING BUT the base64 in the file.
```
cat base64File.txt | base64 -d 
```
At the end of the output will be the file name!
FLAG: ORIGIN.exe

# But where?
To Solve:
https://www.dcode.fr/whitespace-language
Copy and paste the whitespaces to decode the message 



