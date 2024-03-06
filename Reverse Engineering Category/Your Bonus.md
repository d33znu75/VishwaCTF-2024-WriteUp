# Reverse Engineering Category:

### > Your Bonus challenge :

# > Description :

> I am very kind, and you're my friend too. I was about to share some flags with you, but unfortunately, a ransomware attack occurred on the file containing those flags. All the flags got encrypted by the ransomware. After cross-checking the directories, I found the ransomware file and some other related items.

> I'm going to share that information with you. However, due to the ransomware, I'm unable to provide you with the flags 😥😥. Now, I need your help to recover those flags. Can you assist me, please? Your cooperation would be highly appreciated, and you will receive a reward for your help.

> Note : Ransomware are not meant to be executed as it can harm your systems (although this won't) 

In this challenge, we received a ransomware.exe file and two text files. One of them contained some random characters.

Then, opening the executable file in Ghidra and jumping to the main function to see how it works.

We observe that the application opens a file named "Flags.txt" and writes to it.

So, we used a Python script to reverse the random characters in the "Your_hacked_data0.txt" file, as it's the output of the flag.

```py
# Define the symbols used for encoding
symbols = ['#','(','&','*',')','!','%','$','@','^']

# Read data from the file and strip whitespace
with open('Your_hacked_data0.txt', 'r') as file:
    lines = [line.strip() for line in file]

# Function to convert symbols to decimal numbers
def symbols_to_decimal(line):
    decimal_line = ""
    for char in line:
        if char in symbols:
            decimal_line += str(symbols.index(char))
    return decimal_line

# Function to convert decimal numbers to ASCII and search for the flag (format: VISHWACTF)
def decimal_to_ascii(decimal_string):
    for offset in range(50):
        ascii_string = ""
        for i in range(0, len(decimal_string), 2):
            num = int(decimal_string[i:i+2]) + offset
            ascii_string += chr(num)
        if "VISHWACTF" in ascii_string:
            print(ascii_string)

# Process each line in the file
for line in lines:
    decimal_line = symbols_to_decimal(line)
    decimal_to_ascii(decimal_line)
```

FLAG : 
> VISHWACTF[4R3_R4N50MW4R35_B3AUTIFUL]
