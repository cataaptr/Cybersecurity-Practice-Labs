# 🔓 Cracking the Private Key on Metasploitable2 Virtual Machine

## **Key Concepts**
	Brute-Force Attack: A method where the attacker systematically tries every possible combination of characters until the correct password is found. This approach can be very effective against weak passwords.

	John the Ripper: An open-source password cracking tool used to recover weak passwords through various methods, including dictionary and brute-force attacks.

	Hashing: A process that converts passwords into fixed-size strings using a hash function, allowing systems to store passwords securely by saving only their hashes instead of the actual passwords.

	Password Dictionary: A collection of common passwords and phrases used by cracking tools to quickly test against password hashes, exploiting the tendency of users to choose weak passwords.

	SSH (Secure Shell): A secure network protocol for accessing and managing devices over an unsecured network, providing encrypted communication and strong authentication.


>Note: Always use strong, unique passwords to protect your accounts. Common passwords, such as "1234567," are easily cracked and put your accounts at risk.


## Steps:

> **Note:** Replace `YOUR_IP_ADDRESS` with the actual IP address of your target machine when following these steps.

1. **Create a New User on Metasploitable2:**
   - I created a new user named `cati` with the password `1234` and verified that both machines could communicate using the ping command:
     ```bash
     sudo adduser cati
     su - cati
     ```

2. **Generate an Encrypted Key for SSH Login:**
   - Generated an SSH key with the password `abc123`:
     ```bash
     ssh-keygen
     ```

3. **Set Up the `.ssh` Directory and Authorized Keys:**
   - Navigated to the `.ssh` directory, created an authorized keys file, and set read/write permissions for the user:
     ```bash
     cd ~/.ssh/
     ls -la
     touch authorized_keys
     chmod 600 authorized_keys
     cat id_rsa.pub >> authorized_keys
     ```

4. **Obtain the Private Key on Kali Linux:**
   - Transferred the private key via HTTP:
     ```bash
     python -m SimpleHTTPServer
     wget http://YOUR_IP_ADDRESS:8000/id_rsa
     cat id_rsa
     ```

5. **Install SSH2John on the Local Machine:**
   - Downloaded the `ssh2john.py` script into a directory named `sshTutorial` on the Desktop:
     ```bash
     wget https://raw.githubusercontent.com/magnumripper/JohnTheRipper/bleeding-jumbo/run/ssh2john.py
     ```

6. **Extract the Private Key Hash:**
   - Retrieved the private key hash on the local machine:
     ```bash
     python3 ssh2john.py id_rsa > id_rsa.hash
     cat *hash
     ls *hash
     john --wordlist=/usr/share/john/password.lst id_rsa.hash
     ```
		![printScreen1](https://github.com/cataaptr/Cybersecurity-Practice-Labs/blob/main/img/bruteForce1.png)

7. **Apply the Key to the Target:**
   - Copied the private key to the John the Ripper directory and accessed the target machine:
     ```bash
     cp id_rsa /usr/share/john
     ls id*
     ssh -oHostKeyAlgorithms=+ssh-rsa -i id_rsa cati@YOUR_IP_ADDRESS
     ```
		![printScreen2](https://github.com/cataaptr/Cybersecurity-Practice-Labs/blob/main/img/bruteForce2.png)
