# Password Cracking

# Hashcat

Dictionary Attack

```
hashcat hash.txt -m 0 -a 0 /usr/share/wordlists/rockyou.txt

```

1. One specify you want to use hashcat
2. Either create a file with your hashes of the same type or type the single hash.
3. Select mode(can lookup modes on hashcat website)
4. Select attack type(on hashcat site)
5. Select wordlist

Mask Attack

```

hashcat -m 0 -a 3 ./hash.txt 'SKY-HQNT-?d?d?d?d'

```

1. The question mark is a placeholder and the placeholder must have digits hence the d

# Ophcrack

Only For Windows Password

1. Load the hash
2. Choose a table

# PDF

```

pdf2john encrypted.pdf > hash.txt

```

1. You will get the hash of the pdf and it will be stored in hash.txt

Next

```

cat hash.txt | cut -d ":" -f 2- > clean.txt

```

1. This is necessary because pdf2john includes the filename in front of the hash, which is not valid syntax for hashcat.

Now you can crack it with the command below

```

hashcat clean.txt -m 10700 -a 0 /usr/share/wordlists/rockyou.txt

```

# Kali Linux

```

john --format=crypt --wordlist=/usr/share/wordlists/rockyou.txt passwords.txt

```

Must use "--format=crypt" in john to crack Kali Linux passwords

