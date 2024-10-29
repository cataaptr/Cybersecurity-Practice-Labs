# Cracking a Password-Protected ZIP/RAR File

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
