# Forensics

# File Craving

Scenario

The security team detected a strange file (green_file.bin) exiting the network. We need to determine if it contains sensitive information.

Steps to Analyze

1. Identify the File Format

Run the file command to check the file type based on its magic bytes:

```
file green_file.bin

```

2. If the output identifies it as a PNG file, rename it to .png to view it as an image:

```
mv green_file.bin green_file.png

```

3. Examine for Embedded Files Using Binwalk

Use binwalk to check for additional files hidden within green_file:

```

binwalk green_file.png

```
Binwalk will output offsets for any hidden files (e.g., multiple PNGs or compressed files).


4. Extract Hidden Files

Use binwalk’s --extract option to pull out all identified files:

```

binwalk --extract --dd="png:png" green_file.png

```


5. Check the _green_file.extracted directory for the extracted files.

Analyze Extracted Files

If any extracted files are non-image files (e.g., CAB), run the file command:

```

file CAB

```
For compressed files like CAB, extract them:

```
tar xvf CAB

```

Check the extracted directory for any sensitive files, such as flags.txt.

# Magic Bytes/ File Signature

1. Use strings command or cyberchef to idnetify file type

```
strings filename

```

2. Imprt the file in hex Editor
3. Find the proper structure and redo the numbers

# Hidden Data Extraction from .docx Files

Scenario

A .docx file appears to contain hidden information. Let’s extract the contents and locate the hidden data.

Steps to Extract Hidden Information

Convert .docx to .zip

Rename the .docx file to .zip:

```

mv SuperAwesomeDoc.docx SuperAwesomeDoc.zip

```

Extract Contents

Unzip the file to access its internal structure:

```

unzip SuperAwesomeDoc.zip

```

Navigate to Media Files

Go to the word/media directory, where images and media files are stored:

```
cd word/media

```
Identify the Hidden Image
