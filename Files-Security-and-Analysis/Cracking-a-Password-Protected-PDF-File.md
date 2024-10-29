# 📄 Cracking a Password-Protected PDF File

I used John the Ripper to crack a password-protected PDF file with the password "computer." First, I extracted the password hash using the pdf2john tool, which is essential for the cracking process. Then, I use John the Ripper to perform a dictionary attack, testing multiple common passwords against the hash. This example highlights how weak passwords like "computer" can be easily compromised, emphasizing the need for strong, unique passwords to protect sensitive documents.

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
    ![PrintScreen](https://github.com/cataaptr/Cybersecurity-Practice-Labs/blob/main/img/pdf.png)
