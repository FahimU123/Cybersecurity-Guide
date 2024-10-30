# Crytography

# Number Bases

Binary (Base 2): 01001000 01100101 01101100 01101100 01101111

Decoded Message: "Hello"
Explanation: Each 8-bit sequence represents a character in ASCII. For example, 01001000 is H, 01100101 is e, etc.
Octal (Base 8): 110 145 154 154 157

Decoded Message: "Hello"
Explanation: These octal numbers map to ASCII character codes: 110 is H, 145 is e, etc.
Hexadecimal (Base 16): 48 65 6C 6C 6F

Decoded Message: "Hello"
Explanation: Each hex number represents an ASCII character: 48 is H, 65 is e, etc.
Base 32: JBSWY3DP

Decoded Message: "Hello"
Explanation: Base 32 encoding is often used for text in Base32 applications. Here, "JBSWY3DP" decodes to "Hello".
Base 64: SGVsbG8=

Decoded Message: "Hello"
Explanation: Base 64 is often used in data encoding. SGVsbG8= in Base 64 decodes to "Hello" in ASCII text.

# ROT 13

ROT13: A substitution cipher that shifts each letter in the alphabet 13 positions forward. If a letter goes past "Z," it wraps back to the beginning.

Alphabet: Only letters A-Z and a-z are affected. Digits and other characters remain unchanged.
Example: Uryyb in ROT13 represents Hello in plain text.
Explanation: In ROT13, each letter in "Hello" shifts 13 positions forward:

H becomes U
e becomes r
l becomes y
o becomes b

The result, Uryyb, is "Hello" encoded with ROT13. Applying ROT13 again would decode it back to "Hello."

# atbash

Atbash Cipher: A substitution cipher where each letter in the alphabet is mapped to its reverse counterpart. For example, A becomes Z, B becomes Y, and so on. This applies to both uppercase and lowercase letters.

Alphabet: Uses letters A-Z (or a-z for lowercase).
Example: Zyx in Atbash represents Abc in plain text.
Explanation: In the Atbash cipher, each letter in "Abc" is reversed:

A becomes Z
b becomes y
c becomes x
Thus, Zyx is the Atbash-encoded version of "Abc." Applying Atbash again would decode it back to "Abc."

# Morse Code

Morse Code: A system of encoding letters, numbers, and symbols using sequences of dots (.) and dashes (-). Each character has a unique combination of dots and dashes, separated by spaces.

Alphabet: Uses A-Z, 0-9, and some punctuation symbols.
Example: .... . .-.. .-.. --- in Morse Code represents "HELLO" in plain text.
Explanation: In Morse Code, each letter is represented as follows:

H is ....
E is .
L is .-..
O is ---
When decoded, .... . .-.. .-.. --- spells out "HELLO." Morse Code is widely used in telecommunications and can be transmitted by sound, light, or written form.

# Rail Fence

Rail Fence Cipher: A transposition cipher where plaintext is written in a zigzag pattern across multiple "rails" (or rows) and then read row by row to create the ciphertext.

Setup: Choose a number of rails (e.g., 3).
Example: Using 3 rails, HELLO WORLD is encoded as HOLEL WRDLO.
Explanation:

Write "HELLO WORLD" in a zigzag pattern across 3 rails:

H       L       O
  E   L   W   R
    L       D
    
Then, read row by row to get the encoded message: HOLELWRDLO.
Decoding: To decode, reverse the process by placing characters back in the zigzag pattern, then reading along the rails to reveal the plaintext.

# Vigenère Cipher

Vigenère Cipher: A polyalphabetic substitution cipher that uses a keyword to shift letters in the plaintext. Each letter in the keyword determines how much to shift each corresponding letter in the plaintext, cycling through the keyword as needed.

Alphabet: Uses letters A-Z.
Example: Encoding "HELLO" with the keyword "KEY" produces RIJVS.
Explanation:

Write the plaintext ("HELLO") and repeat the keyword ("KEY") to match its length:

Plaintext: H E L L O
Keyword:   K E Y K E
Shift each letter in the plaintext by the alphabetical position of the corresponding letter in the keyword (e.g., K=10, E=4, Y=24):

H shifted by K (10) becomes R
E shifted by E (4) becomes I
L shifted by Y (24) becomes J
L shifted by K (10) becomes V
O shifted by E (4) becomes S
The result, RIJVS, is the Vigenère-encrypted message for "HELLO" with the keyword "KEY".

# Strings

Use command below to get strings from a file. Grep looks for those specific letters in the string.

```
strings Steg1.jpg | grep SKY

```

# RSA
