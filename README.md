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


LAB3A

LAB3B

LAB4A


LAB4B
