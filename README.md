# HTB Legacy


Legacy is a beginner-level machine whichs demonstrates potential security risk of SMB on Windows.
``Server Message Block (SMB)`` is a client-server interaction protocol where cients request a file, and the server provides it to the client. It is a Windows based network.

```SMB``` is an application layered protocol that uses ```TCP``` Port 445 to communicate.


# Skills Required
 * Basic knowledge of Windows
 * Basic knowlegde of Metasploit framework
 * Basic enumeration knowledge for ports and services with ```nmap``` or your preffered enumeration tool
 
# Phase 1 

* nmap -p- -T5 -Pn <IP>
* nmap -p <discovered port> ```script1=vuln``` -T5 <IP>
* nmap -p 445 --script=vul -T5 <IP>

# Phase 2 

* Hosts uses old version of windows ```XP```
* Hosts is vulnerable to a ```RCE``` ```CVE-(ms17-010)```, ```CVE-(ms08-067)```


# Phase 3 

Now that we have found those potential vulnerabilities, lets now search for an exploit that can work against those type of vulnerabilities. You can search them on the https://www.exploit-db.com/

In our case the exploidb database shows us a bunch of explit that we can use against our target. From the list given in the databse we see that we can attack with metasploit.


# Phase 4

* Here we serach for the found vulnerability in metasploit.
* Use the command ```use 0``` to select the exploit intended for our target machine.

![search](https://user-images.githubusercontent.com/61636217/184237225-632223dd-6845-4d68-a3c0-a355b55399f1.png)

* Here we will have to set the target IP nad the hosts IP to complete our exploit.
* We also check if the target is actually vulnerable to a RCE affecting Windows XP

![options](https://user-images.githubusercontent.com/61636217/184237651-8444026e-dfcc-4e34-812b-07b4f1e71da6.png)

* Here run the exploit and get a meterpreter shell and we are NT AUTHORITY\SYSTEM! We have pwned our target and can do further enumeration to retrieve the flags.
* From here you can do other enumerations to get the hashes of all the users and maybe find other misconfiguration in the system.

![shell](https://user-images.githubusercontent.com/61636217/184238127-bba2fe98-ce95-421c-b936-76b0dd299de3.png)


# Disclaimer

This is for educational purposes only. Make sure you have written permissions to hack machines you don't own.