# prisma-error

## 1. step of error
rajdeepsingh@officialrajdeepsingh:~/working/next-prisma$ npx prisma generate
Environment variables loaded from .env
Prisma schema loaded from prisma/schema.prisma
Error: Get Config: Unable to establish a connection to query-engine-node-api library. It seems there is a problem with your OpenSSL installation!
Details: Unable to require(`/home/rajdeepsingh/working/next-prisma/node_modules/prisma/libquery_engine-debian-openssl-3.0.x.so.node`)
 /snap/core20/current/lib/x86_64-linux-gnu/libc.so.6: version `GLIBC_2.33' not found (required by /lib/x86_64-linux-gnu/libcrypto.so.3)

Prisma CLI Version : 4.0.0
rajdeepsingh@officialrajdeepsingh:~/working/next-prisma$ 

## 2 step error
yarn add @prisma/client

## 3. step install glibc-source
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

## step 4
