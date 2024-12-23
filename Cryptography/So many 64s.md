### So many 64s
> Help! My friend stole my flashdrive that had the flag on it. When he gave it back the flag was changed! Can you help me decrypt it?

_**Link :**_ https://mega.nz/#!OHhUyIqA!H9WxSdG1O7eVcCm0dffggNB0-dBemSpBAXiZ0OXJnLk
# Solution
We are given a base64 text that's so long to the point, it makes sense if you have to solve this using a script, so i made one
```
import base64

f = open("flag.txt")
b64data = f.read()

while "_" not in b64data:
    b64data = base64.b64decode(b64data).decode('utf-8')
print(b64data)
```
Flag in CTF often has underscore in it, so i just brute force it until it found one since base64 doesn't use it whatsoever

**ABCTF{pr3tty_b4s1c_r1ght?}**
