Lab 2-3
Install and Use ClamAV 
OS Install:
uname - a
Cat /proc/version 

(https://github.com/user-attachments/assets/369a79fc-7109-4722-b3a3-0241160f934a)

Step 1: Update the Repository
Sudo apt update
(https://github.com/user-attachments/assets/306839e4-be96-43d1-aa4f-91990dd2b07a)

Step 2: Install ClamAV Install the “ClamAV” application alongside the “clamav-daemon” from the standard repository of Ubuntu using the default “apt” package manager: 
sudo apt install clamav clamav-daemon
 ![image](https://github.com/user-attachments/assets/563911b6-dd44-4cb9-8037-b18aaf50e1ee)

Step 3: Verify ClamAV Check the installed version of the “clamav” scanner for verification purposes: 
clamscan –version
 ![image](https://github.com/user-attachments/assets/c6c10618-830e-4e55-9baf-cdeb0afb8621)

sudo systemctl stop clamav-freshclam
 ![image](https://github.com/user-attachments/assets/bc7ae2df-5e31-49c5-a7c0-6415b7e802e0)
sudo freshclam
 ![image](https://github.com/user-attachments/assets/8825d10d-4d6f-4d8d-a295-7dc0162905ab)

sudo systemctl start clamav-freshclam
![image](https://github.com/user-attachments/assets/fb89261c-b374-43c4-9908-890dbe2451d3)

 
Download Updates Using Official Website (Second Method)

sudo cp daily.cvd /var/lib/clamav/ 
 ![image](https://github.com/user-attachments/assets/a3490ded-6304-4855-86b0-85440e9ffb3e)

Create a Test folder for testing
Sudo mkdir Test 
 ![image](https://github.com/user-attachments/assets/fc0ad320-1ae5-4d5e-80bc-cb30378eb829)


sudo wget https://secure.eicar.org/eicar.com.txt
 ![image](https://github.com/user-attachments/assets/9caddd51-b905-4183-bb69-34f28b953eec)


sudo clamscan --infected --remove --recursive Test/
 ![image](https://github.com/user-attachments/assets/54f9999d-57e3-4298-a4c0-6bd9cb1166a4)

sudo nano Clam_HelloWorld.ndb
Then we enter this Clam_HelloWorld:0:*:68656c6c6f*776f726c64 into the file Clam_HelloWorld.ndb. (This file will be signed so that ClamAV can scan the file, specifically if any txt file contains the words "hello" and the word "world" it will be considered to be injected with malicious code)
 ![image](https://github.com/user-attachments/assets/f40df67c-b3e5-4a29-8179-f0cc88fb37a0)

 sudo nano test.txt
clamscan -d Clam_HelloWorld.ndb test.txt


