# Steganography Category:

### > We Are Valorant challenge :

# > Description :

> One day, while playing Valorant, I received a mail from Riot Games that read,

>“In a world full of light, sometimes the shadows help you win.” “Your Signature move also helps you a lot ; develop one and ace it now.”

>It also had an image and a video/gif attached to it. I am not able to understand what they want to say. Help me find what the message wants to express.

In this challenge, we have two attachments: a video/gif of Astra (a Valorant agent) and a broken file that was supposed to be a jpg. I fixed the file signature, and then we got a picture.

While trying some steg tools, I found that there is something inside the image that we need to extract with steghide, but we don't have a password.

Since we have a gif, the only thing we need to do is inspect its frames.

Looking at all frames, we noticed a frame with hidden text "Tenz", so it's the password to get the data inside the image.

![](https://cdn.discordapp.xyz/attachments/1206718275371667506/1213520223005573130/passw.png)

The .txt file extracted from the image contains:

```
Hello!!
hope you are enjoying the CTF
here's your flag

VishwaCTF{you_are_invited_to_the_biggest_valorant_event}
```


FLAG : 
> VishwaCTF{you_are_invited_to_the_biggest_valorant_event}
