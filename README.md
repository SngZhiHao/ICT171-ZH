# ICT171-ZHIHAO
ZhiHaoGitHub


LAB 1A

Get familiarize with setting up Ubuntu VMWare, configuration of network and resolving the network issue. I have to go to network and sharing center to disable both the VMWare internet and it works after disabling it. I have to use NAT network instead of the bridged network
systemctl list-units --type=service (to check services)
sudo systemctl start [service] - I tested on NetworkManager.services
sudo systemctl status to check on the status

grep -r 'search-term'
touch test.txt
chmod 777 test.txt (read/write/execute all enabled)

Install Google chrome .deb file
cd Downloads/ to go to the path, ls to list down the files (google-chrome-stable_current_amd64.deb)
sudo apt install --> to install the google chrome, if failed use sudo dkpg -i (sudo is admin(root), dpkg is debian package manager, -i is install)

sudo apt install vlc
sudo apt search vlc (search packages)

LAB 1B

sudo apt update
sudo apt install apache2 Install apache2 server
sudo apt install nmap 

wget file from website
wget https://www.gutenberg.org/files/76/76-0.txt
wget https://www.gutenberg.org/files/36/36-0.txt
wge https://www.gutenberg.org/files/12/12-0.txt

mkdir books (create directory)
move the files
tar cf books.tar books
bzip2 books.tar
ls -la

add user/group

sudo adduser alice, sudo adduser bob, sudo adduser mallory
sudo groupadd sharedgroup
sudo mkdir /home/shared/
sudo touch /home/shared/file{1..10}
sudo usermod -aG sharedgroup alice, sudo usermod -aG sharedgroup bob, sudo suermod -aG sharedgroup mallory (add to group)
sudo chmod -R 770 /home/shared/ (Allow owner)
sudo chmod 750 /home/shared/ (Read write execute for to group) - dont need to put *
sudo gpasswd -d mallory sharedgroup (remove from sharedgroup)



LAB 2A
Total Cost Ownshership (TCO)

<img width="470" height="271" alt="image" src="https://github.com/user-attachments/assets/7aa27d59-8e4f-44dd-b451-6ce6c07ab5bc" />


LAB 2B-1

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
Tried using https://, the browser will continue to load but to no availability.

Downloading files
wget http://www.eecs.berkeley.edu/Pubs/TechRpts/2009/EECS-2009-28.pdf (download successful)

<img width="926" height="236" alt="image" src="https://github.com/user-attachments/assets/3f83daa6-6c2b-4dcf-a6cb-3b93fd9b9ada" />

sudo cp EECS-2009-28.pdf /var/www/html/ (to move file into this directory)
http://13.229.111.158/EECS-2009-28.pdf tested this link to see whether I can access the files

<img width="660" height="482" alt="image" src="https://github.com/user-attachments/assets/6c533705-ea80-4c20-b7db-e023352bd6b2" />

create a link in the index.html using the EECS-2009-28 PDF File
< ahref="EECS-2009-28.pdf">Click here</a>

<img width="590" height="204" alt="image" src="https://github.com/user-attachments/assets/688ed7ee-ab7d-482b-b626-1a07dc5500ba" />

Tested using other computer to access the link and it also works.

Some other alternatives to Amazon EC2 - Microsoft Azure, Google cloud, Oracle cloud INfrastructure

curl command basically is to show the entire index.html webpage configurations

LAB 2b-2
Creaet and navigate directories
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
(Add bash script)
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


Creating and executing basic bash scripts
Hello, World Script
<img width="341" height="40" alt="image" src="https://github.com/user-attachments/assets/3907ba83-d34b-45c0-90a9-ad1c2ed50890" />

Implementing Loops and Conditionals
It shows the user, loop through the next five numbers, and also create a conditional statement script

<img width="364" height="112" alt="image" src="https://github.com/user-attachments/assets/4a8f424e-88bd-4002-8361-ce86c9199c15" />

Autoating System Monitoring Tasks
Basically to show how many times the user want to monitor the system as shown from the sreenshot

<img width="407" height="246" alt="image" src="https://github.com/user-attachments/assets/06218b07-ef80-4d55-b65b-1330a1577148" />




REFLECTION
mkdir dirname --> create new directory
cat filename --> view contents without opening in a GUI
chmod 777 command is used for changing/allowing permission to read write execute
#!/bin/bash is to tell the system to use the Bash shell interpreter to run the script
free -h shows the image below, it shows the total,used, free, shared, buff/cache information

<img width="401" height="38" alt="image" src="https://github.com/user-attachments/assets/c2282f79-46a4-4cc0-b597-d25f5f1db308" />



ps -aux | grep httpd (to check apache2 server working/active)

LAB3A
Domain Registration (using GoDaddy)


NSlookup domain

<img width="408" height="155" alt="image" src="https://github.com/user-attachments/assets/26a896a0-f2ca-4dc9-9c79-97430e66ee49" />

Dig domain

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


LAB3B

Sample directory (backup)
mkdir -p /home/ubuntu/Documents/testfolder
cd /home/ubuntu/Documents

<img width="417" height="58" alt="image" src="https://github.com/user-attachments/assets/71da4883-b496-4e09-b784-b4126019e13b" />

Creates files

<img width="404" height="89" alt="image" src="https://github.com/user-attachments/assets/f655efe0-77c7-4c72-bb51-1cc28642b20e" />

Write bash script (adding timestamp filename)

Perofrm backup of files and compressing files

<img width="409" height="242" alt="image" src="https://github.com/user-attachments/assets/26ecde8d-d21b-44ff-be62-050b5463a7c4" />


LAB4A


LAB4B
