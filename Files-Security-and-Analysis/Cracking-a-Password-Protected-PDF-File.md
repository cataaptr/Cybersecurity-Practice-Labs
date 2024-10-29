# Cracking a Password-Protected PDF File

## Steps:

1. **Create a Password-Protected PDF File:**
   - Created a password for a PDF file, with the password being `computer`:
     ```bash
     pdftk test.pdf output output.pdf userpw computer
     ```

2. **Store the Hash:**
   - Extracted the password hash using `pdf2john`:
     ```bash
     pdf2john output.pdf > test.txt
     ```

3. **Crack the Password:**
   - Used `John the Ripper` to check if it can find the password:
     ```bash
     sudo john test.txt --wordlist=/usr/share/john/password.lst
     ```

- Within seconds, the password was successfully found.
    ![PrintScreen](https://github.com/cataaptr/Cybersecurity-Practice-Labs/blob/main/img/zip1.png)