<h1>Decrypt an Encrypted Message</h1>

<h2>Description</h2>
In this section, I will delve into the decryption of encrypted messages, a crucial aspect of cybersecurity and data protection. I will explore the process of decrypting an encrypted file using a Caesar cipher and the AES-256 encryption algorithm. I'll start by discovering hidden clues to reveal the necessary decryption command, then apply the command to recover the original content from an encrypted file. This project demonstrates key cryptographic concepts such as cipher decryption, key-based encryption, and file recovery.

<h2>Languages and Utilities Used</h2>

- <b>Shell Commands</b>

<h2>Environments Used</h2>

- <b>Linux</b>

<h2>Program Walk-through:</h2>

<h3>1. Reading the Contents of a File</h3>
<p align="center">
<img src="https://i.imgur.com/XaME3iJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
This file is a ransom note indicating that the data has been encrypted and provides instructions on how to recover it. I need to look for a hidden file in the Caesar subdirectory.  
<br/>

<br/> 
 
<h3>2. Find the Hidden File</h3>
<p align="center">
<img src="https://i.imgur.com/nPHQcPZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
After navigating to the Caesar directory, listing its contents and then displaying the contents of the hidden file, I see a file named .leftShift3. This file contains an encrypted message in a Caesar cipher form. The command <code>cat .leftShift3 | tr "d-za-cD-ZA-C" "a-zA-Z"</code> reads the .leftShift3 file and translates the encoded message back to its original readable form. The pipe operator (|) redirects the output of the first command (<code>cat .leftShift3</code>) as input to the second command (<code>tr "d-za-cD-ZA-C" "a-zA-Z"</code>), which performs the character translation to decode the message.

<br/>
<br/>

<h3>3. Decrypt the File</h3>
<p align="center">
<img src="https://i.imgur.com/wl5Z0ec.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>The command <code>openssl aes-256-cbc -pbkdf2 -a -d -in Q1.encrypted -out Q1.recovered -k ettubrute</code> is used to decrypt an encrypted file.</p>
<ul>
  <li><code>openssl</code>: The command-line tool for cryptography operations.</li>
  <li><code>aes-256-cbc</code>: Specifies the AES encryption algorithm with a 256-bit key in CBC mode.</li>
  <li><code>-pbkdf2</code>: Uses PBKDF2 for key derivation.</li>
  <li><code>-a</code>: Specifies base64 encoding/decoding.</li>
  <li><code>-d</code>: Decrypt mode.</li>
</ul>


<h2>Conclusion</h2>
I successfully decrypted an encrypted file by first solving a Caesar cipher and then using the AES-256 encryption algorithm. This exercise highlights the importance of strong encryption and the risks of weak ciphers in cybersecurity. It demonstrates how attackers can exploit weak encryption methods if not properly implemented, underscoring the need for robust encryption techniques to ensure data integrity and confidentiality in digital systems.
