# RSA Twins - 90 Points
> Aww, twins :). Theyâre so cute! They must be (almost) identical because theyâre the same except for the slightest difference. Anyway, see if you can find my flag. Hint: This is just math. You're probably not going to find any sort of specialized attack.

_**Link :**_ https://mega.nz/#!2aBwFCKa!NWQKRIbYzSAU2iwCPNppO7SE92W6sne4FKD3sKE2A-k
### Solution
You thought that this is a literal Twin RSA encryption huh? well too bad because that's not it, don't worry cuz i got pranked too, it turns out the factorization of n doesn't give anything whatsoever when you used greatest common divisor (GCD)

![image](https://github.com/user-attachments/assets/7be7b532-dd41-4b49-b979-20746e442058)

So what is it? the description did said something about them being almost identical which i assume it's the factorization of the n, in which yes they do, you can factorize the n using [factordb](https://factordb.com/).
```
n = 14783703403657671882600600446061886156235531325852194800287001788765221084107631153330658325830443132164971084137462046607458019775851952933254941568056899

p = 121588253559534573498320028934517990374721243335397811413129137253981502291629
q = 121588253559534573498320028934517990374721243335397811413129137253981502291631
```
The only difference they have is their last 2 digits number. Since the only hint that the challenge gave is the fact they have almost identical number, this makes me wonder if the way to get the flag is just your standard RSA decryption way? being :

1. Factorize the n
2. Use the factorization (two prime numbers) of n to get phi
3. Inverse the phi with the public key
4. c (ciphertext) raised to the power of inverse modulo n
5. Turn the large integer into bytes

Plus, they didn't used some small or large public key, it's just your average public key, so it's safe to assume that this isn't going to be a hassle, so let's break this RSA
```py
from Crypto.Util.number import *

n = 14783703403657671882600600446061886156235531325852194800287001788765221084107631153330658325830443132164971084137462046607458019775851952933254941568056899
e = 65537
c = 684151956678815994103733261966890872908254340972007896833477109225858676207046453897176861126186570268646592844185948487733725335274498844684380516667587

n1 = 121588253559534573498320028934517990374721243335397811413129137253981502291629
n2 = 121588253559534573498320028934517990374721243335397811413129137253981502291631

phi = (n1-1)*(n2-1)
d = inverse(e, phi)
print(long_to_bytes(pow(c, d, n)))
```
```sh
┌──(myenv)(ibnuraffi㉿kali)-[~/Desktop/ctflearn/kripto]
└─$ python solve.py 
b'flag{i_l0v3_tw1N_pr1m3s}'
```
And yeah, not a single Twin RSA vulnerability involved. But RSA is RSA, so nice challenge :D
