# Symbolic Decimals - 80 Points
> Did you know that you can hide messages with symbols? For example, !@#$%^&*( is 123456789!<br /> Now Try: ^&,*$,&),!@#,*#,!!^,(&,!!$,(%,$^,(%,*&,(&,!!$,!!%,(%,$^,(%,&),!!!,!!$,(%,$^,(%,&^,!)%,!)@,!)!,!@% However, this isn't as easy as you might think.
### Solution
The way the encryption works, can be seen on your keyboard. For example ! is 1 and @ is 2 and based off of that info, you can kind of tell that the entire encrypted message is decimals, so let's decode it. For coma, i assume it's just space since there's no given clue for it whatsoever.
```py
s="^&,*$,&),!@#,*#,!!^,(&,!!$,(%,$^,(%,*&,(&,!!$,!!%,(%,$^,(%,&),!!!,!!$,(%,$^,(%,&^,!)%,!)@,!)!,!@%"
s1=""
l=len(s)
c=0
l=l-1
while c<=l:
      ch=s[c]
      if ch=='!':
         s1=s1 +'1'
      elif ch =='@':
         s1=s1+'2'
      elif ch =='#':
         s1=s1+'3'
      elif ch =='$':
         s1=s1+'4'
      elif ch =='%':
         s1=s1+'5'
      elif ch =='^':
         s1=s1+'6'
      elif ch =='&':
         s1=s1+'7'
      elif ch =='*':
         s1=s1+'8'
      elif ch =='(':
         s1=s1+'9'
      elif ch ==')':
         s1=s1+'0'
      else:
          s1=s1+' '
      c=c+1
print(s1)
```
I used the above script made by this guy [@ashutoshg547](https://ashutoshg547.medium.com/?source=post_page---byline--c6ee24bba391--------------------------------), you can checkout the dude's write up of this challenge [here](https://ashutoshg547.medium.com/symbolic-decimals-ctflearn-c6ee24bba391). The script works like how i explained it above.

![image](https://github.com/user-attachments/assets/1a03bdc5-a13f-4ebd-9aa3-ff4cb0a2f94b)

I use cyberchef to decrypt the decimals, and we got the flag

![image](https://github.com/user-attachments/assets/d8658445-7202-4a37-b5f9-97029ab5f9c4)
```
CTF{Star_._Wars_._For_._Life}
```
