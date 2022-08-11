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
