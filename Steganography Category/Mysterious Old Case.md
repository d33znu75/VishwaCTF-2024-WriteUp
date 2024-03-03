# Steganography Category:

### > Mysterious Old Case challenge :

# > Description :

> You as a FBI Agent, are working on a old case involving a ransom of $200,000. After some digging you recovered an audio recording.

In this challenge, we have an MP3 file. While listening to it, we hear someone talking in reverse in the middle of the song. After reversing that part, we hear the following message:

```
I sm John Cooper. It is 24th of November, 1971. Now I have left from Seattle and headed towards Reno. I've got all my demands fulfilled. I have done some changes in the flight log and uploaded it to a remote server. The file is encrypted. The hint for decryption is the airliner that I was flying in. Most importantly, the secret key is split and hidden in every element of the Fibonacci series starting from two.
```

In the EXIF metadata of the MP3 file, we have a link to a drive containing many flight logs and a hint for the password to access the flight log:

```
Comment                         : password for the zip is all lowecase with no spaces
User Defined URL                : https://drive.google.com/file/d/1bkuZRLKOGWB7tLNBseWL34BoyI379QbF/view?usp=drive_lin
```

Since this case is related to D.B. Cooper (a famous plane hijack), we know that the flight log is for Flight 305, and the password is the name of the airliner he was flying during the hijack.

password : northwestorientairlines

therefore the flight log looks like this:

```
1971-11-24 06:22:08.531691 - ATT - Boeing 727
V
i
1971-11-24 07:31:08.531691 - HWR - Boeing 727
s
1971-11-24 06:22:08.531691 - ATT - Boeing 727
1971-11-24 07:31:08.531691 - HWR - Boeing 727
h
1971-11-24 06:22:08.531691 - ATT - Boeing 727
1971-11-24 06:22:08.531691 - ATT - Boeing 727
1971-11-24 06:22:08.531691 - ATT - Boeing 727
1971-11-24 07:31:08.531691 - HWR - Boeing 727
w
1971-11-24 07:31:08.531691 - HWR - Boeing 727
1971-11-24 06:22:08.531691 - ATT - Boeing 727
1971-11-24 06:22:08.531691 - ATT - Boeing 727
1971-11-24 07:31:08.531691 - HWR - Boeing 727
1971-11-24 07:31:08.531691 - HWR - Boeing 727
1971-11-24 07:31:08.531691 - HWR - Boeing 727
1971-11-24 06:22:08.531691 - ATT - Boeing 727
a
...
```
So I applied a Python script to extract the characters from the file, since they are in a Fibonacci sequence.

FLAG : 
> VishwaCTF{1_W!LL_3E_B@CK}
