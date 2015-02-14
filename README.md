# University of Illinois at Urbana-Champaign Cloud Computing Specialisation 

## Cloud Computing Concepts

### Development Environment Setup and Configuration

In light of the nature of the Cloud Computing Concepts course a development environment provided as a platform-as-a-service (PaaS) by [Koding](https://koding.com) on their free-tier is recommended for those course participants preferring not to install development tools on their primary computer. 

#### Create an Account

0. Visit the [Koding](https://koding.com) website.
1. Enter your email address and password then click Sign-up to create a new account, or click on the GitHub icon to use an existing GitHub account.
2. A verification code will be sent to your email account and is required before the Koding account and initial virtual machine will be created.
3. You will be prompted to turn-on the virtual machine (koding-vm-0). Click the "Turn it on" button.

The message "koding-vm-0 is building now" will be displayed. Be patient as your virtual machine is built and initialised.

Once the virtual machine instance is ready the sceen changes to a four-pane layout:

* virtual machines (vms) pane
* file manager (folder icon) editor settings (gear icon) pane
* text editor pane (by default)
* the Terminal pane (by default)

#### Install Development Tool-chain Software

Click the mouse in the Terminal to begin the development software installation process.

Either type or copy-and-paste the following commands one-at-a-time into the Terminal pane. To paste a command right-click with the mouse and select Paste from the context-sensitive menu.
Be sure to press the ENTER key after each command.

	(VM) unixscripter: ~ $ sudo apt-get update 
	(VM) unixscripter: ~ $ sudo apt-get upgrade

When prompted to continue press the ENTER key to accept the default response ('Y' - yes).

If prompted about the GRUB bootloader select the default option by pressing the SPACE key until you see an asterisk (\*) appear between the brackets as shown.
 
        [*] /dev/xvda (3221 MB; ???)
 
Press the ENTER key to continue.
 
If prompted about the menu.lst press the ENTER key to accept the default as shown.
 
        keep the local version currently installed

Either type or copy-and-paste the following commands one-at-a-time into the Terminal pane. To paste a command right-click with the mouse and select Paste from the context-sensitive menu.
Be sure to press the ENTER key after each command.

	(VM) unixscripter: ~$ sudo apt-get install build-essential gcc-4.7-locales\ 
			 g++-multilib automake1.9 libtool flex bison gdb gcc-4.7-multilib\ 
			 autoconf2.13 libstdc++6-4.7-dbg libgcc1-dbg autoconf automake g++-4.7\ 
			 unzip dos2unix   

When prompted to continue press the ENTER key to accept the default response ('Y' - yes).

#### Enable Remote Authentication & Access to the Virtual Machine 

To add an SSH key for secure authentication configure your virtual machine to allow remotely-initiated SSH sessions. An example showing the SSH public and private key-pair creation with a passphrase for enhanced security is shown below. **Only required to transfer files but useful for remotely accessing the virtual machine via a secure shell client.**

*Note:* When prompted for a passphrase type a string of characters easy for you to remember but difficult for an attacker to guess.

	(VM) unixscripter: ~ $ mkdir -p ~/.ssh 
	(VM) unixscripter: ~ $ touch ~/.ssh/authorized_keys      

	(VM) unixscripter: ~ $ ssh-keygen
	Generating public/private rsa key pair.
	Enter file in which to save the key (/home/unixscripter/.ssh/id_rsa): 
	Enter passphrase (empty for no passphrase): 
	Enter same passphrase again: 
	Your identification has been saved in /home/unixscripter/.ssh/id_rsa.
	Your public key has been saved in /home/unixscripter/.ssh/id_rsa.pub.
	The key fingerprint is:
	d6:69:4d:41:66:b2:41:6b:1b:b1:a9:ca:e8:2a:57:11 unixscripter@unixscripter
	The key's randomart image is:
	+--[ RSA 2048]----+
	|         .=.=    |
	|    E      @ .   |
	|     .    B .    |
	|    .    + *     |
	|     .  S = .    |
	|    .o o .       |
	|   .. o          |
	|. ..             |
	| o...            |
	+-----------------+


	(VM) unixscripter: ~ $ ls -la ~/.ssh                                                                                                                                                                
	total 20
	drwxr-xr-x 2 unixscripter unixscripter 4096 Feb 10 23:28 .
	drwxr-xr-x 9 unixscripter unixscripter 4096 Feb 10 23:26 ..
	-rw-r--r-- 1 unixscripter unixscripter    0 Feb 10 23:29 authorized_keys
	-rw------- 1 unixscripter unixscripter 1766 Feb 10 23:28 id_rsa
	-rw-r--r-- 1 unixscripter unixscripter  407 Feb 10 23:28 id_rsa.pub

	(VM) unixscripter: ~ $ cat ~/.ssh/id_rsa.pub > ~/.ssh/authorized_keys    

	(VM) unixscripter: ~ $ cat ~/.ssh/id_rsa         
	-----BEGIN RSA PRIVATE KEY-----
	Proc-Type: 4,ENCRYPTED
	DEK-Info: AES-128-CBC,F73341272B55A21700A43597C7CFBB1F
 
	v4fOd/tpYikAWkoYBQCmSV5iVTXPwgAeJOgwFq0IvTW4DSQiFpGgZoqvvXg6wy9V
	/kimQPQZSJ9b3ue7lYgr32b+HKERw/LVgvrNTT2Cu5/JLuA+ShfOiI16GMq4I87a
	/dAFOT07GY4Jrvx9jam8hrIPTfp7fLySxDopu1lWbtcG7LKBS1IgoTXcAmi1tT9L
	eDmnkG6X2WJeGjfHITbzilnx70goMhufyyJutiKPklYLREm5t8kCMQkTZpvw3gLj
	///ade6BeW2qkfyMjksFUkk6fl98w9LB7xuZBkjcAdSU342itXttgCBBKZDs2dKR
	5LTGyGjM0buop0476j0I2510HvHYQjB4Wq+LVtA8qX+UEIAymYqs6FA6Ncbj6gxv
	NQNGG9WncNuLBXbHKUuzzNnZFDWPJ5OVYVYmGbpKMsC7XkrQTeh5DJXwk4JPSiip
	601WX4VL4LAHaYx0dpFdmccxWKHMEFFHpswxTqL3BAUvCS2+cTPhQvu49FQzIAgf
	VlE2wTToyrG2b4NOQa88ierJukdnJF7dF0dex5UHAqjTYCOZnATRwmUNojGnZYNg
	IIsxlZvYN/un7yXFa/Btw6Yo+tvmvx3ZMUq4Hi5dxLvFMkYkV16lGdHrd7A90h28
	SLtqKco1LnUk13jAOJcJeLQRl8n3zAnwxF5wgC8+t6cl0JMnxTztJgMFv8oz/x7p
	xY3apVjpdcLVzXxNg4tflZavrT2stThybD20fex2nZUMGeF/S58YYQC6tEN1iYfd
	ZCLAriimbqxk9BBVVRwDEv8zUXF3Oh110ApwfQX1xZXbD/EgR6E4c4WtzniTtbPv
	j+HMIpNWBCCje9OWbOq4qHpmou6CnQt0/I8zvl4Y64X6A+9B0kfpbTFriq3+1vH9
	2hJNn5zF5ETD0XYbmIBOaIx6B2Vmqh8/44aTSGeaEE5+F/Co5lrDpYw2kbwEDiw7
	Zxp+QLHVZkN8M/PB5l7YdfDDu0IMKmnq5+zWZv0PDwlOddXAL75cSlZUPHNHRftb
	g9GOrLAGrEJvRBOvD091uOdn00aDVy+LU0pxaKbyetrR9qo2P1MfIokpTS3885Nm
	sRUZlrE4WIvf/2EZtKUupVTMWDh2J8YzPoXuKH/4yrHG326tchLuxls3X7Ha7nV3
	uOP8gj438wmmIlOwPty6C8eztzkUAOTV0dp4o1EB1PBzUoWGjOrQJ4RiUrRe35z6
	xPsYncObSyAPzIJ3Yq4fASp9gEKZOW9mHz8Op3lqurT76r+V9INXbqsBaN1aTrcC
	BJu7Yxanglv9t3JLw8dMMWkWhk4Ef/fUMq05EJdi3Np978qkfjZjlANCDPyBGIJQ
	fSi/usWh8O90nOXRafQzMKr/5X0NL47NZ/Ugjzy9B6CbGEVzIhCdFjwA8c1C2AVK
	AcYR3BGmU5HjUHih7r5VZKaqlVNxqIIzaTnGoCEgltvhcjCWSqyIKlJAAsOooy5G
	WYWEPsEZm5y7l9OdLbXiO4mHHGxadjP1AajNX7kzi4atU4bxXmsc6dEjwVkYsqM5
	ReUAF9alR8oskSTtXtJwuuKC+ZWwMhskLe+fRIrchESvtODbR5RvQRKUJkmZRgeG
	-----END RSA PRIVATE KEY-----

**Copy the private key (~/.ssh/id_rsa) to your local computer and save it in a file accessible only to yourself.** Delete the ~/.ssh/id\_rsa file from the virtual machine to prevent an attacker from obtaining your private key; this key is required to access the virtual machine via the secure session protocol. The ~/.ssh/id\_rsa.pub file is the associated public key and can be given to anyone with whom you wish you communicate securely; do NOT delete it from the virtual machine.

	(VM) unixscripter: ~ $ rm ~/.ssh/id_rsa

On your local computer set the permissions on the .pem file (VM: id\_rsa, PC: unixscripter.pem) as indicated, if using any \*nix system. You can name the .pem file something other then unixscripter.pem on your own local computer.

For \*nix systems:

	(PC) mouse@ratnest: ~ $ chmod 600 unixscripter.pem
	(PC) mouse@ratnest: ~ $ ls -l *.pem
	-rw------- 1 mouse mouse 1767 Feb 10 19:42 /home/mouse/unixscripter.pem

For Apple Mac OS X systems:

        (PC) mouse@ratnest: ~ $ chmod 600 unixscripter.pem
        (PC) mouse@ratnest: ~ $ ls -l *.pem
        -rw------- 1 mouse mouse 1767 Feb 10 19:42 /Users/mouse/unixscripter.pem

For Microsoft Windows systems there is no need to set these permissions and the .pem file can be saved to the default folder or anywhere you chose.

Click koding-vm-0. A circle containing three dots appears to the immediate right. Click on the circle. The DNS name of your virtual machine is the 'Assigned URL'. You will need this name to remotely access the virtual machine via an SSH and/or to copy files to and from this virtual machine. Click on the actual name to open a new web browser tab from which you can copy the full URL (e.g. uukk84b7906a.unixscripter.koding.io). Close the new web browser tab.

Click anywhwere in the web browser tab containing your workspace (https://koding.com/IDE/koding-vm-0/my-workspace).

#### Access the Virtual Machine and Workspace

There are two ways to access to the virtual machine: the Koding login page or a secure shell client. 

To verify remote access via an SSH client, including [PuTTY](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html), use the following example to successfully login to your virtual machine.
 
        (PC) mouse@ratnest: ~$ ssh -i unixscripter.pem\ 
                                 unixscripter@uukk84b7906a.unixscripter.koding.io
 
When you are presented with the following prompt type 'yes' (no quotation marks) and press the ENTER key. You will only see this message the first time you attempt to access your virtual mach
ine from a computer on which you have nor previously connected to uukk84b7906a.unixscripter.koding.io.
 
        The authenticity of host 'uukk84b7906a.unixscripter.koding.io (54.186.21.0)' can't be established.
        ECDSA key fingerprint is 9b:47:a8:c0:1d:89:f9:a5:85:94:21:32:5e:50:f6:cc.
        Are you sure you want to continue connecting (yes/no)?
 
        Enter passphrase for key '/home/mouse/unixscripter.pem':
 
You should see the text below displayed in a terminal window.
 
>Welcome to Ubuntu 14.04 LTS (GNU/Linux 3.13.0-29-generic x86\_64)
>
> * Documentation:  https://help.ubuntu.com/
>
>  System information as of Tue Feb 10 22:23:21 UTC 2015
>
>  System load: 0.31              Memory usage: 6%   Processes:       114
>  Usage of /:  51.4% of 2.82GB   Swap usage:   0%   Users logged in: 0
>
>  Graph this data and manage this system at:
>    https://landscape.canonical.com/
>
>  Get cloud support with Ubuntu Advantage Cloud Guest:
>    http://www.ubuntu.com/business/services/cloud
>
>The programs included with the Ubuntu system are free software;
>the exact distribution terms for each program are described in the
>individual files in /usr/share/doc/\*/copyright.
>
>Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
>applicable law.
>
> \*\*\* System restart required \*\*\*
>
>unixscripter@unixscripter:~$

After upgrading the system software the "System restart required" message is displayed when accessing the virtual machine via a secure shell client. To restart the virtual machine:
 
* type the command 'sudo reboot', or
* position the mouse cursor over the virtual machine name (koding-vm-0) and click on the circle filled with three dots; toggle the On/Off switch
 
To logout of the remote session from your local computer and disconnect from the virtual machine simply type:
 
        (PC) unixscripter: ~ $ logout

Transferring a file from your local computer to the virtual machine in a secure manner is as easy as either of these commands.

	(VM) unixscripter: ~ $ wget\ 
				https://d396qusza40orc.cloudfront.net/\
				cloudcomputing/assignments/mp1_assignment.zip -o mp1_assignment.zip

	(PC) mouse@ratnest:~$ scp -i unixscripter.pem mp1_assignment.zip\ 
			 unixscripter@uukk84b7906a.unixscripter.koding.io:~/mp1_assignment.zip
	Enter passphrase for key '/home/mouse/unixscripter.pem': 
	mp1_assignment.zip                            100%  444KB 443.8KB/s   00:00

	(VM) unixscripter: ~ $ ls
	Applications  Backup  Documents  README.md  Web  mp1_assignment.zip

#### Compile Process Test for Machine Programming 1 (MP1) - Unmodified Template Version

	(VM) unixscripter: ~ $ mkdir cloudcomputing
	(VM) unixscripter: ~ $ cd cloudcomputing
	(VM) unixscripter: ~/cloudcomputing $ unzip ../mp1_assignment.zip  

	(VM) unixscripter: ~/cloudcomputing $ make
	(VM) unixscripter: ~/cloudcomputing $ ./Application
	Configuration (i.e., *.conf) file File Required
	(VM) unixscripter: ~/cloudcomputing $  

At this point you have confirmed a properly configured development environment and successfully compiled the application.

#### Miscellaneous

To produce a portable document formatted (PDF) document from text file(s) install these packages.

	(VM) unixscripter: ~ $ sudo apt-get install enscript lpr ghostscript

The enscript utility can convert your source code files into a single document which can be read or printed after transferring the document to your local computer.

	(VM) unixscripter: ~/cloudcomputing $ enscript {Application,EmulNet,Log,MP1Node\
				Member,Param,Queue,stdincludes}.{h,cpp} --no-header --output=- \
				| ps2pdf - > assignment.pdf
	(PC) mouse@ratnest: ~$ scp -i ~unixscripter.pem\
				unixscripter@uukk84b7906a.unixscripter.koding.io:\
				~/cloudcomputing/assignment.pdf assignment.pdf


