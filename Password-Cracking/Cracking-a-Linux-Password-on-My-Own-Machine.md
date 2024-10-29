# 🔓 Cracking a Linux Password on My Own Machine

I used **John the Ripper** to crack a password on my own machine. The process involved utilizing a password hash and a predefined dictionary of common passwords. By extracting the password hash and testing it against the entries in the dictionary, I aimed to find a matching password. This method illustrates how even simple passwords can be compromised, emphasizing the importance of using strong, unique passwords for security.

> “123456” is one of the most commonly used passwords in the world, making it an easy target for a hacker attempting a brute-force attack.
> Most Easiest Passwords to Crack
>    123456
>    password
>    123456789
>    12345678
>    12345
>    1234567
>    111111
>    123123
>    qwerty
>    abc123
>
> ⚠️ Given that there are existing dictionaries of common passwords available on the internet, we should be more cautious about our password choices. Using strong, unique passwords is essential for protecting our accounts and sensitive information.

## Steps: 

1. **Create a New User:** 
    - I created a new user named `user2` with the password `user2` using the following commands:
      ```bash
      useradd -r user2  
      passwd user2
      ```

2. **Store the Password Hash:** 
    - I extracted the password hash and modified the file to retain only the hash for `user2`:
      ```bash
      sudo unshadow passwd shadow > /home/catalina/Desktop/linuxpass.txt
      ```

3. **Attempt to Crack the Password:** 
    - I used John the Ripper to check if the password could be found in the dictionary, but it was not successful:
      ```bash
      sudo john --format=crypt linuxpass.txt --wordlist=/usr/share/john/password.lst
      ```
      ![PrintScreen](https://github.com/cataaptr/Cybersecurity-Practice-Labs/blob/main/img/pass1.png)

4. **Change the Password:** 
    - I navigated to the password dictionary, changed user2’s password to "tamara," which I found in the dictionary, and then reapplied the previous steps. This time, the password was successfully cracked.
      ![PrintScreen](https://github.com/cataaptr/Cybersecurity-Practice-Labs/blob/main/img/pass2.png)

