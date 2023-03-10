# PBL-Project3
Implement Web solution based on MERN stack in AWS Cloud

## Challenges Encountered_Lessons learnt
Each projects i attempt upskills my proficiency in the use of Linux commands, i spent longer hours on the projects because of my zero experience in navigating Linux command. Thankfully the Engineers at Darey.io would always guide, but then the personal researches i did for myself online helped alot. I always try not to immediately run to the Engineers at Darey.io, i have come to understand that personnally troubleshooting why i got a different outcome...far from the expected outcome based on the project steps guide, has helped grow my confidence.

In this project i learnt how to edit a file using VIM command, i also learnt to always crosscheck your script, any missed letter will impact the expected outcome.


In this project, i will implement a web solution based on MERN stack in AWS Cloud.
MERN Web stack consists of following components:
MongoDB: A document-based, No-SQL database used to store application data in a form of documents.
ExpressJS: A server side Web Application framework for Node.js.
ReactJS: A frontend framework developed by Facebook. It is based on JavaScript, used to build User Interface (UI) components.
Node.js: A JavaScript runtime environment. It is used to run JavaScript on a machine rather than in a browser.

![PBL3_Picture1](https://user-images.githubusercontent.com/122687798/219295295-2f4b71f3-bb5b-4651-aea2-313b81faa2c3.JPG)

As shown on the illustration above, a user interacts with the ReactJS UI components at the application front-end residing in the browser. This frontend is served by the application backend residing in a server, through ExpressJS running on top of NodeJS.

Any interaction that causes a data change request is sent to the NodeJS based Express server, which grabs data from the MongoDB database if required, and returns the data to the frontend of the application, which is then presented to the user.


## STEP 1 – BACKEND CONFIGURATION

ubuntu@ip-172-31-51-131:~$
ubuntu@ip-172-31-51-131:~$
ubuntu@ip-172-31-51-131:~$
ubuntu@ip-172-31-51-131:~$ sudo apt update
Hit:1 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy InRelease
Get:2 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates InRelease [119 kB]
Get:3 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports InRelease [107 kB]
Get:4 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]
Get:5 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/universe amd64 Packages [14.1 MB]
Get:6 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/universe Translation-en [5652 kB]
Get:7 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/universe amd64 c-n-f Metadata [286 kB]
Get:8 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/multiverse amd64 Packages [217 kB]
Get:9 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/multiverse Translation-en [112 kB]
Get:10 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy/multiverse amd64 c-n-f Metadata [8372 B]
Get:11 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 Packages [896 kB]
Get:12 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main Translation-en [196 kB]
Get:13 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 c-n-f Metadata [13.5 kB]
Get:14 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 Packages [624 kB]
Get:15 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/restricted Translation-en [96.1 kB]
Get:16 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/restricted amd64 c-n-f Metadata [580 B]
Get:17 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 Packages [811 kB]
Get:18 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/universe Translation-en [147 kB]
Get:19 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/universe amd64 c-n-f Metadata [15.5 kB]
Get:20 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 Packages [9696 B]
Get:21 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/multiverse Translation-en [3260 B]
Get:22 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/multiverse amd64 c-n-f Metadata [456 B]
Get:23 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports/main amd64 Packages [40.7 kB]
Get:24 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports/main Translation-en [9800 B]
Get:25 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports/main amd64 c-n-f Metadata [392 B]
Get:26 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports/restricted amd64 c-n-f Metadata [116 B]
Get:27 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports/universe amd64 Packages [19.5 kB]
Get:28 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports/universe Translation-en [13.8 kB]
Get:29 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports/universe amd64 c-n-f Metadata [392 B]
Get:30 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports/multiverse amd64 c-n-f Metadata [116 B]
Get:31 http://security.ubuntu.com/ubuntu jammy-security/main amd64 Packages [637 kB]
Get:32 http://security.ubuntu.com/ubuntu jammy-security/main Translation-en [133 kB]
Get:33 http://security.ubuntu.com/ubuntu jammy-security/main amd64 c-n-f Metadata [8388 B]
Get:34 http://security.ubuntu.com/ubuntu jammy-security/restricted amd64 Packages [575 kB]
Get:35 http://security.ubuntu.com/ubuntu jammy-security/restricted Translation-en [87.9 kB]
Get:36 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 Packages [640 kB]
Get:37 http://security.ubuntu.com/ubuntu jammy-security/universe Translation-en [88.1 kB]
Get:38 http://security.ubuntu.com/ubuntu jammy-security/universe amd64 c-n-f Metadata [11.3 kB]
Get:39 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 Packages [4960 B]
Get:40 http://security.ubuntu.com/ubuntu jammy-security/multiverse Translation-en [996 B]
Get:41 http://security.ubuntu.com/ubuntu jammy-security/multiverse amd64 c-n-f Metadata [240 B]
Fetched 25.8 MB in 4s (5747 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
7 packages can be upgraded. Run 'apt list --upgradable' to see them.
ubuntu@ip-172-31-51-131:~$
ubuntu@ip-172-31-51-131:~$ sudo apt upgrade
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
The following NEW packages will be installed:
  linux-aws-headers-5.15.0-1030 linux-headers-5.15.0-1030-aws linux-image-5.15.0-1030-aws
  linux-modules-5.15.0-1030-aws
The following packages have been kept back:
  ubuntu-advantage-tools
The following packages will be upgraded:
  git git-man less linux-aws linux-headers-aws linux-image-aws
6 upgraded, 4 newly installed, 0 to remove and 1 not upgraded.
6 standard LTS security updates
Need to get 53.4 MB of archives.
After this operation, 231 MB of additional disk space will be used.
Do you want to continue? [Y/n] Y
Get:1 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 less amd64 590-1ubuntu0.22.04.1 [143 kB]
Get:2 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 git-man all 1:2.34.1-1ubuntu1.8 [953 kB]
Get:3 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 git amd64 1:2.34.1-1ubuntu1.8 [3141 kB]Get:4 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-modules-5.15.0-1030-aws amd64 5.15.0-1030.34 [22.5 MB]
Get:5 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-image-5.15.0-1030-aws amd64 5.15.0-1030.34 [11.4 MB]
Get:6 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-aws amd64 5.15.0.1030.28 [1716 B]Get:7 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-image-aws amd64 5.15.0.1030.28 [2458 B]
Get:8 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-aws-headers-5.15.0-1030 all 5.15.0-1030.34 [12.4 MB]
Get:9 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-headers-5.15.0-1030-aws amd64 5.15.0-1030.34 [2822 kB]
Get:10 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates/main amd64 linux-headers-aws amd64 5.15.0.1030.28 [2390 B]
Fetched 53.4 MB in 2s (33.9 MB/s)
(Reading database ... 63605 files and directories currently installed.)
Preparing to unpack .../0-less_590-1ubuntu0.22.04.1_amd64.deb ...
Unpacking less (590-1ubuntu0.22.04.1) over (590-1build1) ...
Preparing to unpack .../1-git-man_1%3a2.34.1-1ubuntu1.8_all.deb ...
Unpacking git-man (1:2.34.1-1ubuntu1.8) over (1:2.34.1-1ubuntu1.6) ...
Preparing to unpack .../2-git_1%3a2.34.1-1ubuntu1.8_amd64.deb ...
Unpacking git (1:2.34.1-1ubuntu1.8) over (1:2.34.1-1ubuntu1.6) ...
Selecting previously unselected package linux-modules-5.15.0-1030-aws.
Preparing to unpack .../3-linux-modules-5.15.0-1030-aws_5.15.0-1030.34_amd64.deb ...
Unpacking linux-modules-5.15.0-1030-aws (5.15.0-1030.34) ...
Selecting previously unselected package linux-image-5.15.0-1030-aws.
Preparing to unpack .../4-linux-image-5.15.0-1030-aws_5.15.0-1030.34_amd64.deb ...
Unpacking linux-image-5.15.0-1030-aws (5.15.0-1030.34) ...
Preparing to unpack .../5-linux-aws_5.15.0.1030.28_amd64.deb ...
Unpacking linux-aws (5.15.0.1030.28) over (5.15.0.1028.26) ...
Preparing to unpack .../6-linux-image-aws_5.15.0.1030.28_amd64.deb ...
Unpacking linux-image-aws (5.15.0.1030.28) over (5.15.0.1028.26) ...
Selecting previously unselected package linux-aws-headers-5.15.0-1030.
Preparing to unpack .../7-linux-aws-headers-5.15.0-1030_5.15.0-1030.34_all.deb ...
Unpacking linux-aws-headers-5.15.0-1030 (5.15.0-1030.34) ...
Selecting previously unselected package linux-headers-5.15.0-1030-aws.
Preparing to unpack .../8-linux-headers-5.15.0-1030-aws_5.15.0-1030.34_amd64.deb ...
Unpacking linux-headers-5.15.0-1030-aws (5.15.0-1030.34) ...
Preparing to unpack .../9-linux-headers-aws_5.15.0.1030.28_amd64.deb ...
Unpacking linux-headers-aws (5.15.0.1030.28) over (5.15.0.1028.26) ...
Setting up less (590-1ubuntu0.22.04.1) ...
Setting up linux-aws-headers-5.15.0-1030 (5.15.0-1030.34) ...
Setting up git-man (1:2.34.1-1ubuntu1.8) ...
Setting up linux-headers-5.15.0-1030-aws (5.15.0-1030.34) ...
Setting up linux-headers-aws (5.15.0.1030.28) ...
Setting up git (1:2.34.1-1ubuntu1.8) ...
Setting up linux-image-5.15.0-1030-aws (5.15.0-1030.34) ...
I: /boot/vmlinuz is now a symlink to vmlinuz-5.15.0-1030-aws
I: /boot/initrd.img is now a symlink to initrd.img-5.15.0-1030-aws
Setting up linux-image-aws (5.15.0.1030.28) ...
Setting up linux-modules-5.15.0-1030-aws (5.15.0-1030.34) ...
Setting up linux-aws (5.15.0.1030.28) ...
Processing triggers for man-db (2.10.2-1) ...
Processing triggers for linux-image-5.15.0-1030-aws (5.15.0-1030.34) ...
/etc/kernel/postinst.d/initramfs-tools:
update-initramfs: Generating /boot/initrd.img-5.15.0-1030-aws
/etc/kernel/postinst.d/zz-update-grub:
Sourcing file `/etc/default/grub'
Sourcing file `/etc/default/grub.d/40-force-partuuid.cfg'
Sourcing file `/etc/default/grub.d/50-cloudimg-settings.cfg'
Sourcing file `/etc/default/grub.d/init-select.cfg'
Generating grub configuration file ...
GRUB_FORCE_PARTUUID is set, will attempt initrdless boot
Found linux image: /boot/vmlinuz-5.15.0-1030-aws
Found initrd image: /boot/microcode.cpio /boot/initrd.img-5.15.0-1030-aws
Found linux image: /boot/vmlinuz-5.15.0-1028-aws
Found initrd image: /boot/microcode.cpio /boot/initrd.img-5.15.0-1028-aws
Warning: os-prober will not be executed to detect other bootable partitions.
Systems on them will not be added to the GRUB boot configuration.
Check GRUB_DISABLE_OS_PROBER documentation entry.
done
Scanning processes...
Scanning linux images...

No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
ubuntu@ip-172-31-51-131:~$
ubuntu@ip-172-31-51-131:~$ curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -

## Installing the NodeSource Node.js 18.x repo...


## Populating apt-get cache...

+ apt-get update
Hit:1 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy InRelease
Hit:2 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates InRelease
Hit:3 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports InRelease
Hit:4 http://security.ubuntu.com/ubuntu jammy-security InRelease
Reading package lists... Done

## Confirming "jammy" is supported...

+ curl -sLf -o /dev/null 'https://deb.nodesource.com/node_18.x/dists/jammy/Release'

## Adding the NodeSource signing key to your keyring...

+ curl -s https://deb.nodesource.com/gpgkey/nodesource.gpg.key | gpg --dearmor | tee /usr/share/keyrings/nodesource.gpg >/dev/null

## Creating apt sources list file for the NodeSource Node.js 18.x repo...

+ echo 'deb [signed-by=/usr/share/keyrings/nodesource.gpg] https://deb.nodesource.com/node_18.x jammy main' > /etc/apt/sources.list.d/nodesource.list
+ echo 'deb-src [signed-by=/usr/share/keyrings/nodesource.gpg] https://deb.nodesource.com/node_18.x jammy main' >> /etc/apt/sources.list.d/nodesource.list

## Running `apt-get update` for you...

+ apt-get update
Hit:1 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy InRelease
Hit:2 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-updates InRelease
Hit:3 http://us-east-1.ec2.archive.ubuntu.com/ubuntu jammy-backports InRelease
Hit:4 http://security.ubuntu.com/ubuntu jammy-security InRelease
Get:5 https://deb.nodesource.com/node_18.x jammy InRelease [4563 B]
Get:6 https://deb.nodesource.com/node_18.x jammy/main amd64 Packages [774 B]
Fetched 5337 B in 1s (5310 B/s)
Reading package lists... Done

## Run `sudo apt-get install -y nodejs` to install Node.js 18.x and npm
## You may also need development tools to build native addons:
     sudo apt-get install gcc g++ make
## To install the Yarn package manager, run:
     curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | gpg --dearmor | sudo tee /usr/share/keyrings/yarnkey.gpg >/dev/null
     echo "deb [signed-by=/usr/share/keyrings/yarnkey.gpg] https://dl.yarnpkg.com/debian stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
     sudo apt-get update && sudo apt-get install yarn


ubuntu@ip-172-31-51-131:~$ sudo apt-get install -y nodejs
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  nodejs
0 upgraded, 1 newly installed, 0 to remove and 1 not upgraded.
Need to get 28.5 MB of archives.
After this operation, 186 MB of additional disk space will be used.
Get:1 https://deb.nodesource.com/node_18.x jammy/main amd64 nodejs amd64 18.14.0-deb-1nodesource1 [28.5 MB]
Fetched 28.5 MB in 0s (70.3 MB/s)
Selecting previously unselected package nodejs.
(Reading database ... 92360 files and directories currently installed.)
Preparing to unpack .../nodejs_18.14.0-deb-1nodesource1_amd64.deb ...
Unpacking nodejs (18.14.0-deb-1nodesource1) ...
Setting up nodejs (18.14.0-deb-1nodesource1) ...
Processing triggers for man-db (2.10.2-1) ...
Scanning processes...
Scanning linux images...

No services need to be restarted.
No services need to be restarted.

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
ubuntu@ip-172-31-51-131:~$ node -v
v18.14.0
ubuntu@ip-172-31-51-131:~$ npm -v
9.3.1
ubuntu@ip-172-31-51-131:~$ mkdir Todo
ubuntu@ip-172-31-51-131:~$ ls
Todo
ubuntu@ip-172-31-51-131:~$ cd Todo
ubuntu@ip-172-31-51-131:~/Todo$ npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help init` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (todo)
version: (1.0.0)
description: A todo app
entry point: (index.js)
test command:
git repository:
keywords: todo application
author: Eze Onoky
license: (ISC)
About to write to /home/ubuntu/Todo/package.json:

{
  "name": "todo",
  "version": "1.0.0",
  "description": "A todo app",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [
    "todo",
    "application"
  ],
  "author": "Eze Onoky",
  "license": "ISC"
}


Is this OK? (yes) yes
npm notice
npm notice New minor version of npm available! 9.3.1 -> 9.5.0
npm notice Changelog: https://github.com/npm/cli/releases/tag/v9.5.0
npm notice Run npm install -g npm@9.5.0 to update!
npm notice
ubuntu@ip-172-31-51-131:~/Todo$ ls
package.json
ubuntu@ip-172-31-51-131:~/Todo$

## INSTALL EXPRESSJS

Remember that Express is a framework for Node.js, therefore a lot of things developers would have programmed is already taken care of out of the box. Therefore it simplifies development, and abstracts a lot of low level details. For example, Express helps to define routes of your application based on HTTP methods and URLs.


ubuntu@ip-172-31-51-131:~/Todo$ npm install express

added 57 packages, and audited 58 packages in 2s

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ touch index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ npm install dotenv

added 1 package, and audited 59 packages in 463ms

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ubuntu@ip-172-31-51-131:~/Todo$
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ node index.js
Server running on port 5000
ubuntu@ip-172-31-51-131:~/Todo$ mkdir routes
ubuntu@ip-172-31-51-131:~/Todo$ cd routes
ubuntu@ip-172-31-51-131:~/Todo/routes$ touch api.js
ubuntu@ip-172-31-51-131:~/Todo/routes$ vim api.js
ubuntu@ip-172-31-51-131:~/Todo/routes$ ubuntu@ip-172-31-51-131:~/Todo/routes$
ubuntu@ip-172-31-51-131:~/Todo/routes$

![PBL3_Picture2](https://user-images.githubusercontent.com/122687798/219301120-7c74adb6-144a-4567-a2c1-6a910670b2d7.JPG)

## MODELS

Now comes the interesting part, since the app is going to make use of Mongodb which is a NoSQL database, we need to create a model. A model is at the heart of JavaScript based applications, and it is what makes it interactive. We will also use models to define the database schema . This is important so that we will be able to define the fields stored in each Mongodb document.

In essence, the Schema is a blueprint of how the database will be constructed, including other data fields that may not be required to be stored in the database. These are known as virtual properties.To create a Schema and a model, install mongoose which is a Node.js package that makes working with mongodb easier

ubuntu@ip-172-31-51-131:~/Todo$ npm install express

added 57 packages, and audited 58 packages in 2s

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ touch index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ npm install dotenv

added 1 package, and audited 59 packages in 463ms

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ubuntu@ip-172-31-51-131:~/Todo$
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ node index.js
Server running on port 5000


mkdir routes
:qa
cd

sudo -i
curl -s http://169.254.169.254/latest/meta-data/public-ipv4
:q
q
exit
ubuntu@ip-172-31-51-131:~/Todo$ npm install express

added 57 packages, and audited 58 packages in 2s

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ touch index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ npm install dotenv

added 1 package, and audited 59 packages in 463ms

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ubuntu@ip-172-31-51-131:~/Todo$
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ node index.js
Server running on port 5000ubuntu@ip-172-31-51-131:~/Todo$ npm install express

added 57 packages, and audited 58 packages in 2s

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ touch index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ npm install dotenv

added 1 package, and audited 59 packages in 463ms

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ubuntu@ip-172-31-51-131:~/Todo$
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ node index.js
Server running on port 5000

ubuntu@ip-172-31-51-131:~/Todo$ npm install express

added 57 packages, and audited 58 packages in 2s

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ touch index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ npm install dotenv

added 1 package, and audited 59 packages in 463ms

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ubuntu@ip-172-31-51-131:~/Todo$
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ node index.js

ubuntu@ip-172-31-51-131:~/Todo$ npm install express

added 57 packages, and audited 58 packages in 2s

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ touch index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ npm install dotenv

added 1 package, and audited 59 packages in 463ms

7 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ubuntu@ip-172-31-51-131:~/Todo$
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  node_modules  package-lock.json  package.json
ubuntu@ip-172-31-51-131:~/Todo$ node index.js
Server running on port 5000^C
ubuntu@ip-172-31-51-131:~/Todo$ mkdir routes
ubuntu@ip-172-31-51-131:~/Todo$ cd routes
ubuntu@ip-172-31-51-131:~/Todo/routes$ touch api.js
ubuntu@ip-172-31-51-131:~/Todo/routes$ vim api.js
ubuntu@ip-172-31-51-131:~/Todo/routes$ ubuntu@ip-172-31-51-131:~/Todo/routes$
ubuntu@ip-172-31-51-131:~/Todo/routes$ npm install mongoose

added 102 packages, and audited 161 packages in 6s

12 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo/routes$ cd
ubuntu@ip-172-31-51-131:~$ cd Todo/
ubuntu@ip-172-31-51-131:~/Todo$ npm install mongoose

up to date, audited 161 packages in 836ms

12 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
ubuntu@ip-172-31-51-131:~/Todo$ mkdir models
ubuntu@ip-172-31-51-131:~/Todo$ cd models
ubuntu@ip-172-31-51-131:~/Todo/models$ touch todo.js
ubuntu@ip-172-31-51-131:~/Todo/models$ ls
todo.js
ubuntu@ip-172-31-51-131:~/Todo/models$ vim todo.js
ubuntu@ip-172-31-51-131:~/Todo/models$ ubuntu@ip-172-31-51-131:~/Todo/models$
ubuntu@ip-172-31-51-131:~/Todo/models$
ubuntu@ip-172-31-51-131:~/Todo/models$ cat todo.js

const mongoose = require('mongoose');
const Schema = mongoose.Schema;

//create schema for todo
//const TodoSchema = new Schema({
//action: {
//type: String,
//required: [true, 'The todo text field is required']
//}
//})
//
////create model for todo
//const Todo = mongoose.model('todo', TodoSchema);
//
//module.exports = Todo;
ubuntu@ip-172-31-51-131:~/Todo/models$ ls
todo.js
ubuntu@ip-172-31-51-131:~/Todo/models$ cd
ubuntu@ip-172-31-51-131:~$ ls
Todo
ubuntu@ip-172-31-51-131:~$ cd Todo/
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  models  node_modules  package-lock.json  package.json  routes
ubuntu@ip-172-31-51-131:~/Todo$ cd routes/
ubuntu@ip-172-31-51-131:~/Todo/routes$ ls
api.js
ubuntu@ip-172-31-51-131:~/Todo/routes$ cat api.js

const express = require ('express');
const router = express.Router();

router.get('/todos', (req, res, next) => {

});

router.post('/todos', (req, res, next) => {

});


## MONGODB DATABASE

## Challenges Encountered
So there were alot of bugs on the script i ran earlier, attempts at server connection using node index.js command failed, util the bugs were removed. On Mongo DB, I was also unable to successfully connect from my windows terminal until i updated my current IP on the Mongo DB.

STEPS FOLLOWED...
We need a database where we will store our data. For this we will make use of mLab. mLab provides MongoDB database as a service solution (DBaaS), so to make life easy, you will need to sign up for a shared clusters free account, which is ideal for our use case.The signup process was followed.

PS C:\Users\EZEPC\Desktop\DevOps> ssh -i "PBL3_1.pem" ubuntu@ec2-54-160-80-149.compute-1.amazonaws.com
Welcome to Ubuntu 22.04.1 LTS (GNU/Linux 5.15.0-1030-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Fri Feb 17 02:12:27 UTC 2023

  System load:  0.0               Processes:             97
  Usage of /:   29.9% of 7.57GB   Users logged in:       1
  Memory usage: 21%               IPv4 address for eth0: 172.31.51.131
  Swap usage:   0%


 * Introducing Expanded Security Maintenance for Applications.
   Receive updates to over 25,000 software packages with your
   Ubuntu Pro subscription. Free for personal use.

     https://ubuntu.com/aws/pro

Expanded Security Maintenance for Applications is not enabled.

0 updates can be applied immediately.

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Fri Feb 17 00:20:37 2023 from 105.112.182.126
ubuntu@ip-172-31-51-131:~$
ubuntu@ip-172-31-51-131:~$
ubuntu@ip-172-31-51-131:~$
ubuntu@ip-172-31-51-131:~$ ls
Todo
ubuntu@ip-172-31-51-131:~$ cd Todo/
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  models  node_modules  package-lock.json  package.json  routes
ubuntu@ip-172-31-51-131:~/Todo$ cat todo.js
cat: todo.js: No such file or directory
ubuntu@ip-172-31-51-131:~/Todo$ cd models/
ubuntu@ip-172-31-51-131:~/Todo/models$ ls
todo.js
ubuntu@ip-172-31-51-131:~/Todo/models$ cat todo.js

const mongoose = require('mongoose');
const Schema = mongoose.Schema;

//create schema for todo
//const TodoSchema = new Schema({
//action: {
//type: String,
//required: [true, 'The todo text field is required']
//}
//})
//
////create model for todo
//const Todo = mongoose.model('todo', TodoSchema);
//
//module.exports = Todo;
ubuntu@ip-172-31-51-131:~/Todo/models$ vim todo.js
ubuntu@ip-172-31-51-131:~/Todo/models$ cd
ubuntu@ip-172-31-51-131:~$ cd Todo/
ubuntu@ip-172-31-51-131:~/Todo$ cd routes/
ubuntu@ip-172-31-51-131:~/Todo/routes$ ls
api.js
ubuntu@ip-172-31-51-131:~/Todo/routes$ vim api.js
ubuntu@ip-172-31-51-131:~/Todo/routes$ cd..

cd..: command not found
ubuntu@ip-172-31-51-131:~/Todo/routes$
ubuntu@ip-172-31-51-131:~/Todo/routes$ cd
ubuntu@ip-172-31-51-131:~$ cd Todo/
ubuntu@ip-172-31-51-131:~/Todo$ cat .env
DB = 'mongodb+srv://onokyeze:onoky@105.112.182.126/cluster0.o1a750v.mongodb.net?retryWrites=true&w=majority'
ubuntu@ip-172-31-51-131:~/Todo$ ls
index.js  models  node_modules  package-lock.json  package.json  routes
ubuntu@ip-172-31-51-131:~/Todo$ vim index.js
ubuntu@ip-172-31-51-131:~/Todo$ node index.js
(node:1228) [MONGOOSE] DeprecationWarning: Mongoose: the `strictQuery` option will be switched back to `false` by default in Mongoose 7. Use `mongoose.set('strictQuery', false);` if you want to prepare for this change. Or use `mongoose.set('strictQuery', true);` to suppress this warning.
(Use `node --trace-deprecation ...` to show where the warning was created)
Server running on port 5000
Error: querySrv ENOTFOUND _mongodb._tcp.105.112.182.126
    at QueryReqWrap.onresolve [as oncomplete] (node:internal/dns/promises:251:17) {
  errno: undefined,
  code: 'ENOTFOUND',
  syscall: 'querySrv',
  hostname: '_mongodb._tcp.105.112.182.126'
}
^C
ubuntu@ip-172-31-51-131:~/Todo$ cat .env
DB = 'mongodb+srv://onokyeze:onoky@105.112.182.126/cluster0.o1a750v.mongodb.net?retryWrites=true&w=majority'
ubuntu@ip-172-31-51-131:~/Todo$ vim .env
ubuntu@ip-172-31-51-131:~/Todo$ vim .env
ubuntu@ip-172-31-51-131:~/Todo$ ubuntu@ip-172-31-51-131:~/Todo$
ubuntu@ip-172-31-51-131:~/Todo$
ubuntu@ip-172-31-51-131:~/Todo$ node index.js
(node:1243) [MONGOOSE] DeprecationWarning: Mongoose: the `strictQuery` option will be switched back to `false` by default in Mongoose 7. Use `mongoose.set('strictQuery', false);` if you want to prepare for this change. Or use `mongoose.set('strictQuery', true);` to suppress this warning.
(Use `node --trace-deprecation ...` to show where the warning was created)
Server running on port 5000
MongooseServerSelectionError: Could not connect to any servers in your MongoDB Atlas cluster. One common reason is that you're trying to access the database from an IP that isn't whitelisted. Make sure your current IP address is on your Atlas cluster's IP whitelist: https://docs.atlas.mongodb.com/security-whitelist/
    at Connection.openUri (/home/ubuntu/Todo/node_modules/mongoose/lib/connection.js:825:32)
    at /home/ubuntu/Todo/node_modules/mongoose/lib/index.js:411:10
    at /home/ubuntu/Todo/node_modules/mongoose/lib/helpers/promiseOrCallback.js:41:5
    at new Promise (<anonymous>)
    at promiseOrCallback (/home/ubuntu/Todo/node_modules/mongoose/lib/helpers/promiseOrCallback.js:40:10)
    at Mongoose._promiseOrCallback (/home/ubuntu/Todo/node_modules/mongoose/lib/index.js:1285:10)
    at Mongoose.connect (/home/ubuntu/Todo/node_modules/mongoose/lib/index.js:410:20)
    at Object.<anonymous> (/home/ubuntu/Todo/index.js:12:10)
    at Module._compile (node:internal/modules/cjs/loader:1226:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1280:10) {
  reason: TopologyDescription {
    type: 'ReplicaSetNoPrimary',
    servers: Map(3) {
      'ac-1ujm473-shard-00-01.o1a750v.mongodb.net:27017' => [ServerDescription],
      'ac-1ujm473-shard-00-02.o1a750v.mongodb.net:27017' => [ServerDescription],
      'ac-1ujm473-shard-00-00.o1a750v.mongodb.net:27017' => [ServerDescription]
    },
    stale: false,
    compatible: true,
    heartbeatFrequencyMS: 10000,
    localThresholdMS: 15,
    setName: 'atlas-1390n2-shard-0',
    maxElectionId: null,
    maxSetVersion: null,
    commonWireVersion: 0,
    logicalSessionTimeoutMinutes: null
  },
  code: undefined
}
^C
ubuntu@ip-172-31-51-131:~/Todo$ node index.js
(node:1257) [MONGOOSE] DeprecationWarning: Mongoose: the `strictQuery` option will be switched back to `false` by default in Mongoose 7. Use `mongoose.set('strictQuery', false);` if you want to prepare for this change. Or use `mongoose.set('strictQuery', true);` to suppress this warning.
(Use `node --trace-deprecation ...` to show where the warning was created)
Server running on port 5000
Database connected successfully

  
  ![PBL3_2](https://user-images.githubusercontent.com/122687798/219877009-0960814e-5535-4fe7-8bb9-6a305a28cd03.JPG)

  ![PBL3_3](https://user-images.githubusercontent.com/122687798/219877266-674b035a-5ace-4743-a023-f7356b199ea9.JPG)

  
Now that i see ‘Database connected successfully’, it means we have our backend configured. Now we are going to test it.  
 
## Testing Backend Code without Frontend using RESTful API  

## Chalenges encountered

  
So far we have written backend part of our To-Do application, and configured a database, but we do not have a frontend UI yet. We need ReactJS code to achieve that. But during development, we will need a way to test our code using RESTfulL API. Therefore, we will need to make use of some API development client to test our code.

In this project, we will use Postman to test our API. Postman has already been installed on the PC, now to test our API, we will perform CRUD operartions on Postman

CRUD operartions on Postman - CRUD means - Create, Rename, Update Delete any kind of resources using Postman  
  
It is advised to test all the API endpoints and make sure they are working. For the endpoints that require body, you should send JSON back with the necessary fields since it’s what we setup in our code.

Now open your Postman, create a POST request to the API http://<PublicIP-or-PublicDNS>:5000/api/todos. This request sends a new task to our To-Do list so the application could store it in the database.
  
## STEP 2 – FRONTEND CREATION
  
Since we are done with the functionality we want from our backend and API, it is time to create a user interface for a Web client (browser) to interact with the application via API. To start out with the frontend of the To-do app, we will use the create-react-app command to scaffold our app. In the same root directory as your backend code, which is the Todo directory, run:
  
ubuntu@ip-172-31-63-190:~/Todo$ cat package.json
{
  "name": "todo",
  "version": "1.0.0",
  "description": "A todo app",
  "main": "index.js",
  "scripts": {
  "start": "node index.js",
  "start-watch": "nodemon index.js",
  "dev": "concurrently \"npm run start-watch\" \"cd client && npm start\""
  },
  "keywords": [
    "todo",
    "application"
  ],
  "author": "Eze Onoky",
  "license": "ISC",
  "dependencies": {
    "dotenv": "^16.0.3",
    "express": "^4.18.2",
    "mongoose": "^6.9.2"
  },
  "devDependencies": {
    "concurrently": "^7.6.0"
  }
ubuntu@ip-172-31-63-190:~/Todo$ vi package.json
ubuntu@ip-172-31-63-190:~/Todo$ vim package.json
ubuntu@ip-172-31-63-190:~/Todo$ cat package.json

{
  "name": "todo",
  "version": "1.0.0",
  "description": "A todo app",
  "main": "index.js",
  "scripts": {
  "start": "node index.js",
  "start-watch": "nodemon index.js",
  "dev": "concurrently \"npm run start-watch\" \"cd client && npm start\""
  },
  "keywords": [
    "todo",
    "application"
  ],
  "author": "Eze Onoky",
  "license": "ISC",
  "dependencies": {
    "dotenv": "^16.0.3",
    "express": "^4.18.2",
    "mongoose": "^6.9.2"
  },
  "devDependencies": {
    "concurrently": "^7.6.0"
  }
}
ubuntu@ip-172-31-63-190:~/Todo$ ls
client  index.js  models  node_modules  package-lock.json  package.json  routes
ubuntu@ip-172-31-63-190:~/Todo$ cd client/
ubuntu@ip-172-31-63-190:~/Todo/client$ ls
README.md  node_modules  package-lock.json  package.json  public  src
ubuntu@ip-172-31-63-190:~/Todo/client$ vim package.json
ubuntu@ip-172-31-63-190:~/Todo/client$ cat package.json
{
  "name": "client",
  "version": "0.1.0",
  "private": true,
  "dependencies": {
    "@testing-library/jest-dom": "^5.16.5",
    "@testing-library/react": "^13.4.0",
    "@testing-library/user-event": "^13.5.0",
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-scripts": "5.0.1",
    "web-vitals": "^2.1.4"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest"
    ]
  },
  "proxy": "http://localhost:5000",
  "browserslist": {
    "production": [
      ">0.2%",
      "not dead",
      "not op_mini all"
    ],
    "development": [
      "last 1 chrome version",
      "last 1 firefox version",
      "last 1 safari version"
    ]
  }
}
ubuntu@ip-172-31-63-190:~/Todo/client$ cd ..
ubuntu@ip-172-31-63-190:~/Todo$ npm run dev

> todo@1.0.0 dev
> concurrently "npm run start-watch" "cd client && npm start"

[0]
[0] > todo@1.0.0 start-watch
[0] > nodemon index.js
[0]
[1]
[1] > client@0.1.0 start
[1] > react-scripts start
[1]
[0] sh: 1: nodemon: not found
[0] npm run start-watch exited with code 127
[1] (node:8300) [DEP_WEBPACK_DEV_SERVER_ON_AFTER_SETUP_MIDDLEWARE] DeprecationWarning: 'onAfterSetupMiddleware' option is deprecated. Please use the 'setupMiddlewares' option.
[1] (Use `node --trace-deprecation ...` to show where the warning was created)
[1] (node:8300) [DEP_WEBPACK_DEV_SERVER_ON_BEFORE_SETUP_MIDDLEWARE] DeprecationWarning: 'onBeforeSetupMiddleware' option is deprecated. Please use the 'setupMiddlewares' option.
[1] Starting the development server...
[1]
[1] Compiled successfully!
[1]
[1] You can now view client in the browser.
[1]
[1]   Local:            http://localhost:3000
[1]   On Your Network:  http://172.31.63.190:3000
[1]
[1] Note that the development build is not optimized.
[1] To create a production build, use npm run build.
[1]
[1] webpack compiled successfully

![PBL3_4](https://user-images.githubusercontent.com/122687798/219880051-0ca393b6-ae2b-45a3-acc0-7afd66e7a45c.JPG)
  
Your app should open and start running on localhost:3000

Important note: In order to be able to access the application from the Internet you have to open TCP port 3000 on EC2 by adding a new Security Group rule. You already know how to do it.
  
## Creating your React Components
One of the advantages of react is that it makes use of components, which are reusable and also makes code modular. For our Todo app, there will be two stateful components and one stateless component. From your Todo directory run...
cd client  

move to the src directory
cd src
  
Inside your src folder create another folder called components
mkdir components
Move into the components directory with
cd components
  
Inside ‘components’ directory create three files Input.js, ListTodo.js and Todo.js.
touch Input.js ListTodo.js Todo.js

Open Input.js file
vi Input.js
Copy and paste the following  

import React, { Component } from 'react';
import axios from 'axios';

class Input extends Component {

state = {
action: ""
}

addTodo = () => {
const task = {action: this.state.action}

    if(task.action && task.action.length > 0){
      axios.post('/api/todos', task)
        .then(res => {
          if(res.data){
            this.props.getTodos();
            this.setState({action: ""})
          }
        })
        .catch(err => console.log(err))
    }else {
      console.log('input field required')
    }

}

handleChange = (e) => {
this.setState({
action: e.target.value
})
}

render() {
let { action } = this.state;
return (
<div>
<input type="text" onChange={this.handleChange} value={action} />
<button onClick={this.addTodo}>add todo</button>
</div>
)
}
}

export default Input
  
![PBL3_5](https://user-images.githubusercontent.com/122687798/219909746-6a736af4-8921-40c3-9897-96e3d57e2c89.JPG)
  
To make use of Axios, which is a Promise based HTTP client for the browser and node.js, you need to cd into your client from your terminal and run yarn add axios or npm install axios
  
Move to the src folder
cd ..

Move to clients folder
cd ..

Install Axios
npm install axios
  
![PBL3_6](https://user-images.githubusercontent.com/122687798/219909839-e2e97efc-9770-4781-ade2-7c17234834be.JPG)

Sip a coffee, lets continue to our destination
  
## FRONTEND CREATION (CONTINUED) 

Go to ‘components’ directory
cd src/components

After that open your ListTodo.js
vi ListTodo.js

                    in the ListTodo.js copy and paste the following code

import React from 'react';

const ListTodo = ({ todos, deleteTodo }) => {

return (
<ul>
{
todos &&
todos.length > 0 ?
(
todos.map(todo => {
return (
<li key={todo._id} onClick={() => deleteTodo(todo._id)}>{todo.action}</li>
)
})
)
:
(
<li>No todo(s) left</li>
)
}
</ul>
)
}

export default ListTodo
  
                      Then in your Todo.js file you write the following code

import React, {Component} from 'react';
import axios from 'axios';

import Input from './Input';
import ListTodo from './ListTodo';

class Todo extends Component {

state = {
todos: []
}

componentDidMount(){
this.getTodos();
}

getTodos = () => {
axios.get('/api/todos')
.then(res => {
if(res.data){
this.setState({
todos: res.data
})
}
})
.catch(err => console.log(err))
}

deleteTodo = (id) => {

    axios.delete(`/api/todos/${id}`)
      .then(res => {
        if(res.data){
          this.getTodos()
        }
      })
      .catch(err => console.log(err))

}

render() {
let { todos } = this.state;

    return(
      <div>
        <h1>My Todo(s)</h1>
        <Input getTodos={this.getTodos}/>
        <ListTodo todos={todos} deleteTodo={this.deleteTodo}/>
      </div>
    )

}
}

export default Todo; 

                    We need to make little adjustment to our react code. Delete the logo and adjust our App.js to look like this.

                    Move to the src folder
cd ..

                    Make sure that you are in the src folder and run
vi App.js

                    Copy and paste the code below into it

import React from 'react';

import Todo from './components/Todo';
import './App.css';

const App = () => {
return (
<div className="App">
<Todo />
</div>
);
}

export default App;
After pasting, exit the editor.

In the src directory open the App.css

vi App.css
Then paste the following code into App.css:

.App {
text-align: center;
font-size: calc(10px + 2vmin);
width: 60%;
margin-left: auto;
margin-right: auto;
}

input {
height: 40px;
width: 50%;
border: none;
border-bottom: 2px #101113 solid;
background: none;
font-size: 1.5rem;
color: #787a80;
}

input:focus {
outline: none;
}

button {
width: 25%;
height: 45px;
border: none;
margin-left: 10px;
font-size: 25px;
background: #101113;
border-radius: 5px;
color: #787a80;
cursor: pointer;
}

button:focus {
outline: none;
}

ul {
list-style: none;
text-align: left;
padding: 15px;
background: #171a1f;
border-radius: 5px;
}

li {
padding: 15px;
font-size: 1.5rem;
margin-bottom: 15px;
background: #282c34;
border-radius: 5px;
overflow-wrap: break-word;
cursor: pointer;
}

@media only screen and (min-width: 300px) {
.App {
width: 80%;
}

input {
width: 100%
}

button {
width: 100%;
margin-top: 15px;
margin-left: 0;
}
}

@media only screen and (min-width: 640px) {
.App {
width: 60%;
}

input {
width: 50%;
}

button {
width: 30%;
margin-left: 10px;
margin-top: 0;
}
}
Exit

                                In the src directory open the index.css
vim index.css
  
                                 Copy and paste the code below:

body {
margin: 0;
padding: 0;
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Roboto", "Oxygen",
"Ubuntu", "Cantarell", "Fira Sans", "Droid Sans", "Helvetica Neue",
sans-serif;
-webkit-font-smoothing: antialiased;
-moz-osx-font-smoothing: grayscale;
box-sizing: border-box;
background-color: #282c34;
color: #787a80;
}

code {
font-family: source-code-pro, Menlo, Monaco, Consolas, "Courier New",
monospace;
}

                                      Go to the Todo directory
cd ../..

                                      When you are in the Todo directory run:
npm run dev
  

Assuming no errors when saving all these files, our To-Do app should be ready and fully functional with the functionality discussed earlier: creating a task, deleting a task and viewing all your tasks.
  
  
  ![PBL3_7](https://user-images.githubusercontent.com/122687798/219917343-86cb9b60-a9a3-42f4-94af-14a6d2affb85.JPG)

  
  ![PBL3_8](https://user-images.githubusercontent.com/122687798/219917389-78f4f54f-f665-4cf1-8da2-fd8efdee8a26.JPG)

  
  ![PBL3_9](https://user-images.githubusercontent.com/122687798/219917419-60075565-d344-47df-af86-961c7d39425b.JPG)

  
## Congratulations EZE
In this Project #3 I have created a simple To-Do and deployed it to MERN stack. I wrote a frontend application using React.js that communicates with a backend application written using Expressjs. I also created a Mongodb backend for storing tasks in a database. WE MOVE !!!
