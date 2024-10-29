# 📄 Cracking a Password-Protected ZIP/RAR File

I used a tool called John the Ripper to crack a ZIP file, but it also works for RAR files. John the Ripper employs a technique known as a dictionary attack, which involves a predefined set of common and simple passwords. This tool tests each password from the dictionary to see if it matches the hash of the password protecting the file.
For this reason, I set a simple but very common password: "1234567". Using such a weak password makes it easy for the tool to find it quickly, highlighting the importance of choosing strong and unique passwords for better security.


## Steps:

1. **Create a Password-Protected ZIP File:**
   - Created a ZIP file named `Documente.zip` on the Desktop with the simple password: `1234567`
   - Navigated to the Desktop using the command:
     ```bash
     cd Desktop
     ```

2. **Generate the Hash of the Password:**
   - Used a tool called `zip2john` to extract the password hash from the ZIP file. This tool can also be used for RAR files with `rar2john`.
   - Redirected the output to a file named `hash.txt`, which contains the hash of the password (noted between the `$` signs).
     ```bash
     zip2john Documente.zip > hash.txt
     ```

3. **Crack the Password:**
   - Used `John the Ripper` to crack the password using the generated hash.
     ```bash
     john --format=zip hash.txt
     ```

   - Within seconds, the password was successfully found.
    ![PrintScreen](https://github.com/cataaptr/Cybersecurity-Practice-Labs/blob/main/img/zip1.png)
