# MStack

## MStack Apple appstore download site: 

- MStack : 
https://itunes.apple.com/app/id1138210567

- MStackPro: 
https://itunes.apple.com/app/id1148320522

## MStack (Openstack Mobile Client for iPhone/iPad) introduction

  Easy and simple to manage your Openstack cloud from anywhere at any time,
MStack support openstack cloud platform version Icehouce or above verson, 
it use openstack open API to access and manage your cloud environment, 
the app do not need additional register or other actions as long as your
iPhone/iPad have network connection to your openstack cloud environment.

Current Features:

- Support multiple tenants and multiple regions, easy to switch and manage your resources in other tenants/regions at any time

- View resource usage summary

- Create,view,delete,start,stop instances, view instance console logs, associate,disassociate floatingip to your instance.

- View image name,size etc properties
	
- View flavor VCPU,RAM size etc properties
	
- Create,view,delete security group and security group rules
	
- Create,import,delete keypair, save private key to safe place by email

- Create,delete,assocate,disassociate floatingip
	
- Create,delete,edit network
	
- Create,view,edit,delete subnet
	
- Create,view,edit,delete router, add,delete,view router interface set/clear router gateway



## MStack Quick Start
==================

This guide just for newbie who has a little skill in openstack cloud

### MStack Login 
-------------

Host, port, username and password are your openstack cloud keystone
information; you can find them in your openrc file, e.g your openrc file
have the follow lines:

OS\_USERNAME=admin
OS\_PASSWORD=password123
OS\_AUTH\_URL=http://192.168.8.21:5000/v2.0

Input the following information in MStack Login screen:
Host: 192.168.8.21
Port: 5000
User: admin
password: password123


### Create network
--------------
Open MStack App, Go to “Network” list screen , tap navigation bar button
“Add”
input Network name, e.g net1
tap “Done” button

### Create subnet
-------------
Go to “Network” list screen, find your network name, tap “subnet”
button, go to subnet list screen, tap navigation bar button “Add”

Input Subnet name,e.g net1-subnet1
Input Network address, CIDR format, e.g 192.168.1.0/24
Input DNS Servers, e.g 8.8.8.8
Tap “Done”

### Create router
-------------
Go to “Router” list screen
Tap “Add”
Input router name, e.g router1
Choice “External Network”
Tap “Done”

If “External Network” not choice when create router, you can do it by
“Set Gateway” action late

### Set router gateway
------------------
If “external network” not set when you create router, go to “Router”
list screen
Tap “Edit”
Tap “More” at your router row
Tap “Set Gateway” at pop up action list, choice external network 
Tap “Done”

### Add router interface
--------------------
Go to “Router” list screen
Tap “Interface” at your router
Tap “Add”
Choice your subnet name which you just created, e.g net1-subnet1
Tap “Done”

### Create/import keypair
---------------------
Go to “Keypair” list, input keypair name, e.g mykey

Tap “Done”, your private key will display at a text view, you can tap
“mail” navigation button to send your private key out or copy/past the
text to your email body manully, save the private key as a key file at
you desktop host.

If your desktop host exist key pair file, e.g “id\_rsa.pub” is public key 
file in your Linux/Mac user \~/.ssh directory, or create a new one by cmd line
“ssh-keygen -t rsa -f mycloud.key”, you can import the public key to
cloud by MStack.

Send a email to your self with public key file as email body at your
desktop host, Go to MStack App “Keypair” list, input name, Enable switch
“Import public key”, copy/past your public key to “Public Key” text
view, tap “Done” to complete

### Create instance
---------------
Go to “Instance” list screen
Tap “Add”
Input instance name.
Choice Flavor( VM instance size).
Choice boot image, if you cannot see image list, please consult your cloud administrator.
Choice keypair name
Choice Security Group(optinal), if no choice, “default” security group will use
Choice network. If you just one network, you can ignore this option
Tap “Done”

### Associate floatingip
--------------------
Go to “FloatingIP” list
Tap “Add”, choice external network
tap “Done”,

A floatingIP record will create, tap “Edit”, choice the floatingIP row,
tap “Associate” row button, choice a instance port by ipaddress, tape “Done”, 
after that,the vm instance will associate a external IP address, so you can access
the vm instance by floatingIP

### Configure ICMP, SSH Security Group Rules
----------------------------------------
Go to “Security Group” list, choice a security group name which used by
vm instance, e.g “default”
Tap “Add”, choice “All ICMP”, tap “Done”,
repeat the step add “ssh” rule to the security group

### Remote login your instance at your desktop
------------------------------------------
\# ssh –i YourPrivateKey username@floatingIP

if you import .ssh/id\_rsa.pub file to cloud and instance use this
keypair, you can ignore “-i privateKey” file, e.g ssh username@floatingIP
Consult cloud admin about what’s the username



## Screen snapshot:

![Home](https://github.com/alix2013/MStack/blob/master/screensnapshot/Home.png)
![Home](https://github.com/alix2013/MStack/blob/master/screensnapshot/InstanceList.png)
![Home](https://github.com/alix2013/MStack/blob/master/screensnapshot/Overview.png)
![Home](https://github.com/alix2013/MStack/blob/master/screensnapshot/Router.png)


alix2013@icloud.com




