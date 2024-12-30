# So many 64s - 80 Points
> Help! My friend stole my flashdrive that had the flag on it. When he gave it back the flag was changed! Can you help me decrypt it?

_**Link :**_ https://mega.nz/#!OHhUyIqA!H9WxSdG1O7eVcCm0dffggNB0-dBemSpBAXiZ0OXJnLk
### Solution
We are given a base64 text that's so long to the point, it makes sense if you have to solve it using a script, so i made one
```py
import base64

f = open("flag.txt")
data = f.read()

while "_" not in data:
    data = base64.b64decode(data).decode('utf-8')
print(data)
```
Flag in CTF often has underscore in it, so i just brute force it until it found one since base64 doesn't use it whatsoever
```
ABCTF{pr3tty_b4s1c_r1ght?}
```
