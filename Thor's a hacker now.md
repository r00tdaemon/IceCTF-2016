00000000: 4c5a 4950 01b3 007f b61b edf0 8440 58e3  LZIP.........@X.<br>

It was a hexdump of LZIP file. Wrote a quick python script to create the zip file from hex dump.
```
import binascii
f=open("thor.txt","r")
a=f.readlines()
b=[]
data=''
for line in a:
	line=line.split()
	b.append(line[1:9])
for i in b:
	data+=''.join(i)
f2=open("thor2","wb")
f2.write(binascii.unhexlify(data))
f2.close()
f.close()
```
Still it showed couldn't decompress. Used lziprecover<br>
`lziprecover -d thor2`
Done!<br>
<b>IceCTF{h3XduMp1N9_l1k3_4_r341_B14Ckh47}</b>
