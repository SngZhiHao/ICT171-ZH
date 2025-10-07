# ICT171-ZHIHAO
ZhiHaoGitHub


===LAB 1A===

Get familiarize with setting up Ubuntu VMWare, configuration of network and resolving the network issue. I have to go to network and sharing center to disable both the VMWare internet and it works after disabling it. I have to use NAT network instead of the bridged network

systemctl list-units --type=service (to check services)

sudo systemctl start [service] - I tested on NetworkManager.services

sudo systemctl status to check on the status

grep -r 'search-term'
touch test.txt
chmod 777 test.txt (read/write/execute all enabled)

===Install Google chrome .deb file===
cd Downloads/ to go to the path, ls to list down the files (google-chrome-stable_current_amd64.deb)

sudo apt install --> to install the google chrome, if failed use sudo dkpg -i (sudo is admin(root), dpkg is debian package manager, -i is install)

<img width="406" height="158" alt="image" src="https://github.com/user-attachments/assets/8970f9c3-8d37-448b-8113-b00bd5cd10cb" />


sudo apt install vlc

<img width="334" height="233" alt="image" src="https://github.com/user-attachments/assets/9abfdc39-4510-4545-8941-7a9188041db6" />

sudo apt search 'package_name' (search packages)


===LAB 1B===

sudo apt update

sudo apt install apache2 Install apache2 server

Testing the Apache2 Default webpage

<img width="519" height="410" alt="image" src="https://github.com/user-attachments/assets/0063af06-1cd1-4e39-a38a-3dd60feed84d" />


sudo apt install nmap 

wget file from website

wget https://www.gutenberg.org/files/76/76-0.txt

wget https://www.gutenberg.org/files/36/36-0.txt

wge https://www.gutenberg.org/files/12/12-0.txt

<img width="580" height="284" alt="image" src="https://github.com/user-attachments/assets/4b5cbf92-aa84-4d04-89bf-e97285382d88" />


===mkdir books (create directory)===
move the files
tar cf books.tar books
bzip2 books.tar
ls -la

===add user/group===

sudo adduser alice, sudo adduser bob, sudo adduser mallory

sudo groupadd sharedgroup

<img width="406" height="101" alt="image" src="https://github.com/user-attachments/assets/0f16600c-9d6e-44ab-bb1d-65096766c707" />


sudo mkdir /home/shared/

<img width="396" height="58" alt="image" src="https://github.com/user-attachments/assets/c1a676a6-4509-41eb-9de5-8c9314e98fee" />


sudo touch /home/shared/file{1..10}

<img width="395" height="47" alt="image" src="https://github.com/user-attachments/assets/1e440754-be5d-4836-a270-368c36232c10" />

sudo chgrp -R sharedgroup /home/shared

sudo usermod -aG sharedgroup alice, sudo usermod -aG sharedgroup bob, 

sudo chmod -R 770 /home/shared/ (Allow owner and group)

<img width="316" height="133" alt="image" src="https://github.com/user-attachments/assets/3273eacd-bc33-4579-84ec-0d2bde1d3694" />

<img width="722" height="28" alt="image" src="https://github.com/user-attachments/assets/543cdd2a-7d9c-485a-bc55-080bad45e4e7" />

<img width="657" height="276" alt="image" src="https://github.com/user-attachments/assets/e500104a-8f93-4786-94b0-858ed587e138" />

===alice user permission===

<img width="290" height="138" alt="image" src="https://github.com/user-attachments/assets/ed9e5565-6513-4228-a959-483d47c0667e" />

sudo chmod 750 /home/shared/ (Read write execute to group) - dont need to put *

sudo gpasswd -d mallory sharedgroup (remove from sharedgroup)

<img width="390" height="69" alt="image" src="https://github.com/user-attachments/assets/e70ab311-b040-42e4-b8f0-ac4459cfea51" />

===No permission for mallory===

<img width="380" height="84" alt="image" src="https://github.com/user-attachments/assets/432b3235-fe9f-4f6e-a907-5bf3b297704b" />

sudo rm -r /home/shared (to remove all test files and folders) - shared folder is deleted


<img width="332" height="178" alt="image" src="https://github.com/user-attachments/assets/6843de75-53e0-42f6-9cf7-911e5a44306a" />

===Issue deleting user===

<img width="380" height="176" alt="image" src="https://github.com/user-attachments/assets/9e74f5d2-5257-471c-8ec7-d7091d9f0fe0" />

===Removing user===

<img width="380" height="263" alt="image" src="https://github.com/user-attachments/assets/9d751072-cb5f-4d0e-94fd-5b88c809c176" />



===LAB 2A===

===Total Cost Ownshership (TCO)===

<img width="470" height="271" alt="image" src="https://github.com/user-attachments/assets/7aa27d59-8e4f-44dd-b451-6ce6c07ab5bc" />


===LAB 2B-1===

Try out amazon EC2

create a new instance (ubuntu virtual machine)

Configuring security group, add rules HTTP



Install apache

sudo apt update (to update repositories)

sudo apt install apache2

Test on index.html webpage (screenshot attached) using IP address

<img width="669" height="441" alt="image" src="https://github.com/user-attachments/assets/fe18a079-9ab8-4d8d-a034-e6c455ad57c3" />

Edited the index.html using sudo nano/var/www/html/index.html - No permission if don't use sudo

Added my own name to the title page as shown from screenshot above.

===Downloading files===

wget http://www.eecs.berkeley.edu/Pubs/TechRpts/2009/EECS-2009-28.pdf (download successful)

<img width="926" height="236" alt="image" src="https://github.com/user-attachments/assets/3f83daa6-6c2b-4dcf-a6cb-3b93fd9b9ada" />

sudo cp EECS-2009-28.pdf /var/www/html/ (to move file into this directory)

http://13.229.111.158/EECS-2009-28.pdf tested this link to see whether I can access the files

<img width="660" height="482" alt="image" src="https://github.com/user-attachments/assets/6c533705-ea80-4c20-b7db-e023352bd6b2" />

create a link in the index.html using the EECS-2009-28 PDF File

< ahref="EECS-2009-28.pdf">Click here</a>

<img width="590" height="204" alt="image" src="https://github.com/user-attachments/assets/688ed7ee-ab7d-482b-b626-1a07dc5500ba" />

Added another sublink which will redirect to the EECS PDF file above

<img width="722" height="460" alt="image" src="https://github.com/user-attachments/assets/b17fb0a5-25a5-4b86-931f-5c41c5a0bf32" />


Tested using other computer to access the link and it also works.

===Some other alternatives to Amazon EC2 - Microsoft Azure, Google cloud, Oracle cloud infrastructure===

curl command basically is to show the entire index.html webpage configurations

===LAB 2b-2===

===Create and navigate directories===

mkdir lab_test

cd lab_test

create file

touch file1.txt

Copy file

cp file1.txt file2.txt

Rename file

mv file2.txt renamed_file.txt

Delete file

rm renamed_file.txt

Create a text file

nano hell_world.sh

===(Add bash script)===

BASH

#1/bin/bash

echo "Hello, World!"

insert echo "hello, world!"

configure make it executable

chmod 777 hello_world.sh

./hello_world.sh

Other notes:

What is an IP address

4 byte dotted decimal number

has 2 informations: host IP = 192.168.40.35

/16 : 192.168.0.0 = 192.168.0.1 till 192.168.255.253 2^16

192.168.0.0 = network ID

192.168.255.255 Broadcast address

192.168.255.254 Gateway IP

/24 : 196.168.40.0 = 192.168.40.1 to 192.168.168.253 2^24

192.168.40.0 = network ID

192.168.40.255 Broadcast address

192.168.40.254 Gateway IP


===Creating and executing basic bash scripts===

Hello, World Script

<img width="341" height="40" alt="image" src="https://github.com/user-attachments/assets/3907ba83-d34b-45c0-90a9-ad1c2ed50890" />

===Implementing Loops and Conditionals===

It shows the user, loop through the next five numbers, and also create a conditional statement script

<img width="364" height="112" alt="image" src="https://github.com/user-attachments/assets/4a8f424e-88bd-4002-8361-ce86c9199c15" />

===Automating System Monitoring Tasks===

Basically to show how many times the user want to monitor the system as shown from the sreenshot

<img width="407" height="246" alt="image" src="https://github.com/user-attachments/assets/06218b07-ef80-4d55-b65b-1330a1577148" />




===REFLECTION===

mkdir dirname --> create new directory

cat filename --> view contents without opening in a GUI

chmod 777 command is used for changing/allowing permission to read write execute

#!/bin/bash is to tell the system to use the Bash shell interpreter to run the script

free -h shows the image below, it shows the total,used, free, shared, buff/cache information

<img width="401" height="38" alt="image" src="https://github.com/user-attachments/assets/c2282f79-46a4-4cc0-b597-d25f5f1db308" />



ps -aux | grep httpd (to check apache2 server working/active)

===LAB3A===
Domain Registration (using GoDaddy)


NSlookup szhihao.com

<img width="408" height="155" alt="image" src="https://github.com/user-attachments/assets/26a896a0-f2ca-4dc9-9c79-97430e66ee49" />

dig szhihao.com

<img width="455" height="232" alt="image" src="https://github.com/user-attachments/assets/daaecea5-91f1-4161-9a10-0a9836361fcc" />

curl ifconfig.me to see whether can detect

sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
or
Go to the instances in AWS --> security group --> add new inbound rules

sudo apt update
sudo apt install certbot python3-certbot-apache -y

sudo certbot --apache (run to obtain TLS cert)

<img width="749" height="254" alt="image" src="https://github.com/user-attachments/assets/2ed24170-6e8c-4e07-82eb-9bced7ec4626" />

Go to https://szhihao.com

<img width="808" height="467" alt="image" src="https://github.com/user-attachments/assets/190c8d82-1192-4dde-8b54-f09da4910fef" />

Issuer should be **Let's Encrypt**

<img width="600" height="419" alt="image" src="https://github.com/user-attachments/assets/fde37775-cc92-4db0-8744-c3f571e8ff02" />

Enable and test auto-renewal
sudocertbot renew --dry-run

<img width="601" height="193" alt="image" src="https://github.com/user-attachments/assets/d2d4d4ab-d1b8-4e68-b2f8-3ba1b3535843" />


Getting into the domain in Ubuntu Linux VM

<img width="688" height="427" alt="image" src="https://github.com/user-attachments/assets/a09e9edb-90ec-4088-9eda-55be9d5d6f03" />

Install Certbot using snap
sudo apt update
sudo apt install snapd -y
sudo snap install core: sudo snap refresh core
snap snap install --classic certbot
sudo ln -s /snap/bin/certbo /usr/bin/certbot

<img width="371" height="319" alt="image" src="https://github.com/user-attachments/assets/d1fb33ca-c8b3-4a53-8582-9d94f2e5d617" />


===LAB3B===

Sample directory (backup)

Create test files and directory structures and use variables and date formatting
<img width="628" height="191" alt="image" src="https://github.com/user-attachments/assets/075d5877-4074-4cfa-84cf-83e1727ec81c" />


===Perforrm backup of files and compressing files===

<img width="409" height="242" alt="image" src="https://github.com/user-attachments/assets/26ecde8d-d21b-44ff-be62-050b5463a7c4" />


===LAB4A===

===Additional Server Services===

Install MariaDB server and client

Server (sudo apt install mariadb-server)

<img width="397" height="215" alt="image" src="https://github.com/user-attachments/assets/ea3861b5-0b2a-4878-a613-432ac46c5f37" />

Client (sudo apt install mariadb-client)

<img width="387" height="79" alt="image" src="https://github.com/user-attachments/assets/5dbcf9a2-ce56-48bf-a392-3b664f6eb0aa" />

MYSQL not running 

<img width="403" height="154" alt="image" src="https://github.com/user-attachments/assets/30c97b6b-603e-4c11-96c6-f2d62cef7d68" />


Start MYSQL - sudo systemctl start mysql and sudo systemctl status mysql

<img width="404" height="96" alt="image" src="https://github.com/user-attachments/assets/7e87c01b-c348-41f0-86db-6d61d0448624" />


Successful installation of MariaDB (sudo maria-db-secure-installation) - Enhance security

<img width="398" height="221" alt="image" src="https://github.com/user-attachments/assets/5280e953-a145-432d-9bdc-fbd81d550e6e" />

<img width="391" height="306" alt="image" src="https://github.com/user-attachments/assets/9ad52c1d-ac04-43bb-94f1-e73284045053" />


Testing functionality of MariaDB server by logging into the MariaDB database console (sudo mysql -u root -p) 


<img width="407" height="139" alt="image" src="https://github.com/user-attachments/assets/48b7550e-4faa-4454-af54-028d737cc521" />

===Basic DB Operations===

Creating new user application

<img width="406" height="132" alt="image" src="https://github.com/user-attachments/assets/f3679fa0-9c83-4fad-b8d4-e6d8b6c631e2" />

Granting privileges and refreshing the privilege tables

<img width="404" height="154" alt="image" src="https://github.com/user-attachments/assets/cd7d3aca-621e-4676-aba5-a1a89f4e6207" />


Summary

Really appreciate the help from the lecturers, he is very understanding and patient in guiding through the whole session even though there are many difficulties faced in the process. It was quite a tough 4 days for me and I believe for others as well as the schedule is quite tight for the assignment submission and exams. I will say that having submission on the following week of Wednesday and Exam on Saturday is really tough and the UC can maybe take into consideration a 1 week gap for the examination in the future.
