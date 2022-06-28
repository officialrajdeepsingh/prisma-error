# prisma-error

I provide all this command list which run to solve my error but it is not solve.
ubuntu detail and nodejs,yarn,npm latest version. 

PRETTY_NAME="Ubuntu 22.04 LTS"
NAME="Ubuntu"
VERSION_ID="22.04"
VERSION="22.04 LTS (Jammy Jellyfish)"
VERSION_CODENAME=jammy

# 1. step of error
rajdeepsingh@officialrajdeepsingh:~/working/next-prisma$ npx prisma generate
Environment variables loaded from .env
Prisma schema loaded from prisma/schema.prisma
Error: Get Config: Unable to establish a connection to query-engine-node-api library. It seems there is a problem with your OpenSSL installation!
Details: Unable to require(`/home/rajdeepsingh/working/next-prisma/node_modules/prisma/libquery_engine-debian-openssl-3.0.x.so.node`)
 /snap/core20/current/lib/x86_64-linux-gnu/libc.so.6: version `GLIBC_2.33' not found (required by /lib/x86_64-linux-gnu/libcrypto.so.3)

Prisma CLI Version : 4.0.0
rajdeepsingh@officialrajdeepsingh:~/working/next-prisma$ 

# 2 step error
yarn add @prisma/client

# 3. step install glibc-source
rajdeepsingh@officialrajdeepsingh:~$ sudo apt-get update
[sudo] password for rajdeepsingh: 
Ign:1 cdrom://Ubuntu 22.04 LTS _Jammy Jellyfish_ - Release amd64 (20220419) jammy InRelease
Err:2 cdrom://Ubuntu 22.04 LTS _Jammy Jellyfish_ - Release amd64 (20220419) jammy Release
  Please use apt-cdrom to make this CD-ROM recognized by APT. apt-get update cannot be used to add new CD-ROMs
Hit:3 https://brave-browser-apt-release.s3.brave.com stable InRelease          
Hit:4 http://in.archive.ubuntu.com/ubuntu jammy InRelease                      
Hit:5 http://packages.microsoft.com/repos/code stable InRelease                
Hit:6 https://brave-browser-apt-beta.s3.brave.com stable InRelease             
Hit:7 https://download.docker.com/linux/ubuntu jammy InRelease                 
Hit:8 http://in.archive.ubuntu.com/ubuntu jammy-updates InRelease              
Hit:9 http://in.archive.ubuntu.com/ubuntu jammy-backports InRelease            
Get:10 http://security.ubuntu.com/ubuntu jammy-security InRelease [110 kB]     
Get:11 http://apt.postgresql.org/pub/repos/apt jammy-pgdg InRelease [91.7 kB]  
Hit:12 https://ppa.launchpadcontent.net/obsproject/obs-studio/ubuntu jammy InRelease
Get:13 http://apt.postgresql.org/pub/repos/apt jammy-pgdg/main amd64 Packages [238 kB]
Hit:14 https://ppa.launchpadcontent.net/ubuntudde-dev/stable/ubuntu jammy InRelease
Reading package lists... Done
E: The repository 'cdrom://Ubuntu 22.04 LTS _Jammy Jellyfish_ - Release amd64 (20220419) jammy Release' does not have a Release file.
N: Updating from such a repository can't be done securely, and is therefore disabled by default.
N: See apt-secure(8) manpage for repository creation and user configuration details.
N: Skipping acquire of configured file 'main/binary-i386/Packages' as repository 'http://apt.postgresql.org/pub/repos/apt jammy-pgdg InRelease' doesn't support architecture 'i386'
rajdeepsingh@officialrajdeepsingh:~$ sudo apt-get -y install glibc-source
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  glibc-source
0 upgraded, 1 newly installed, 0 to remove and 1 not upgraded.
Need to get 20.7 MB of archives.
After this operation, 26.4 MB of additional disk space will be used.
Get:1 http://in.archive.ubuntu.com/ubuntu jammy/universe amd64 glibc-source all 2.35-0ubuntu3 [20.7 MB]
Fetched 20.7 MB in 34s (617 kB/s)                                              
Selecting previously unselected package glibc-source.
(Reading database ... 217754 files and directories currently installed.)
Preparing to unpack .../glibc-source_2.35-0ubuntu3_all.deb ...
Unpacking glibc-source (2.35-0ubuntu3) ...
Setting up glibc-source (2.35-0ubuntu3) ...

# step 4 install more package not working
rajdeepsingh@officialrajdeepsingh:~/working/next-prisma$ sudo apt-get install libssl-dev
[sudo] password for rajdeepsingh: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Suggested packages:
  libssl-doc
The following NEW packages will be installed:
  libssl-dev
0 upgraded, 1 newly installed, 0 to remove and 1 not upgraded.
Need to get 2,371 kB of archives.
After this operation, 12.4 MB of additional disk space will be used.
Get:1 http://security.ubuntu.com/ubuntu jammy-security/main amd64 libssl-dev amd64 3.0.2-0ubuntu1.5 [2,371 kB]
Fetched 2,371 kB in 4s (565 kB/s)       
Selecting previously unselected package libssl-dev:amd64.
(Reading database ... 218283 files and directories currently installed.)
Preparing to unpack .../libssl-dev_3.0.2-0ubuntu1.5_amd64.deb ...
Unpacking libssl-dev:amd64 (3.0.2-0ubuntu1.5) ...
Setting up libssl-dev:amd64 (3.0.2-0ubuntu1.5) ...

# step 5 not working
rajdeepsingh@officialrajdeepsingh:~/working/next-prisma$ sudo apt-get install -y -q build-essential curl
Reading package lists...
Building dependency tree...
Reading state information...
build-essential is already the newest version (12.9ubuntu3).
curl is already the newest version (7.81.0-1ubuntu1.2).
0 upgraded, 0 newly installed, 0 to remove and 1 not upgraded.

# step 6
rajdeepsingh@officialrajdeepsingh:~/working/next-prisma$ sudo apt-get upgrade libstdc
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
E: Unable to locate package libstdc
rajdeepsingh@officialrajdeepsingh:~/working/next-prisma$ sudo apt-get upgrade libstdc++6
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
libstdc++6 is already the newest version (12-20220319-1ubuntu1).
libstdc++6 set to manually installed.
Calculating upgrade... Done
The following packages will be upgraded:
  libmozjs-91-0
1 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
1 standard security update
Need to get 4,071 kB of archives.
After this operation, 7,168 B disk space will be freed.
Do you want to continue? [Y/n] y
Get:1 http://security.ubuntu.com/ubuntu jammy-security/main amd64 libmozjs-91-0 amd64 91.10.0-0ubuntu1 [4,071 kB]
Fetched 4,071 kB in 6s (701 kB/s)          
(Reading database ... 218431 files and directories currently installed.)
Preparing to unpack .../libmozjs-91-0_91.10.0-0ubuntu1_amd64.deb ...
Unpacking libmozjs-91-0:amd64 (91.10.0-0ubuntu1) over (91.7.0-2) ...
Setting up libmozjs-91-0:amd64 (91.10.0-0ubuntu1) ...
Processing triggers for libc-bin (2.35-0ubuntu3) ...



