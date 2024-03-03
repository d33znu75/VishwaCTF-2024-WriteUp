### > Router |port| challenge :

# > Description :

> There's some unusual traffic on the daytime port, but it isn't related to date or time requests. Analyze the packet capture to retrieve the flag


We were provided with a pcap capture file and instructed to examine the daytime port. Upon analysis, we discovered a text that appeared to be encrypted with ROT13.

After extracting all the encrypted texts and decrypting them using the ROT13 cipher, we were able to reconstruct a complete conversation. This likely contained valuable information relevant to the challenge or investigation at hand.

>Hey, mate!
>Yo, long time no see!
>You sure this mode of communication is still safe?
>Yeah, unless someone else is capturing network packets on the same network we're using. Anyhow, our text is encrypted, and it would be difficult to interpret.
>So let's hope no one else is capturing.
>What's so confidential that you're about to share?
>It's about cracking the password of a person with the username 'Anonymous.'
>Oh wait! Don't you know I'm not so good at password cracking?
>Yeah, I know, but it's not about cracking. It's about the analysis of packets. I've completed most of the job, even figured out a way to get the session key to decrypt and decompress the packets.
>Holy cow! How in the world did you manage to get this key from his device?
>Firstly, I hacked the router of our institute and closely monitored the traffic, waiting for 'Anonymous' to download some software that requires admin privilege to install. Once he started the download, I, with complete control of the router, replaced the incoming packets with the ones I created containing malicious scripts, and thus gained a backdoor access to his device. The further job was a piece of cake.
>Whoa! It's so surprising to see how much you know about networking or hacking, to be specific.
>Yeah, I did a lot of research on that. Now, should we focus on the purpose of this meet?
>Yes, of course. So, what should I do for you?
>Have you started the packet capture as I told you earlier?
>Yes, I did.
>Great! I will be sending his SSL key, so find the password of 'Anonymous.'
>Yes, I would, but I need some details like where to start.
>The only details I have are he uses the same password for every website, and he just went on to register for a CTF event.
>Okay, I will search for it.
>Wait a second, I won't be sending the SSL key on this Daytime Protocol port; we need to keep this untraceable.
>I will be sending it through FTP. Since the file is too large, I will be sending it in two parts. Please remember to merge them before using it. Additionally, some changes may be made to it during transfer due to the method I'm using. Ensure that you handle these issues.
>Okay! ...

After exporting the SSL keys from the ftp-data and discovering that they were encrypted with ROT20, we decrypted the SSL data. Upon importing the decrypted SSL data back into the pcap file, we were able to decrypt all the traffic within the pcap.

Given that we knew the username was "Anonymous", we conducted a simple string search within the decrypted traffic to find the corresponding password. Eventually, we found a password which turned out to be the flag we were seeking.

![](https://cdn.discordapp.com/attachments/1067452256686981161/1213931661331402812/Screen_Shot_2024-03-03_at_8.30.41_PM.png?ex=65f744f5&is=65e4cff5&hm=aa43d235bb5182f2a4f143c4a639e263cf43595dcfe736f07b7c3d64f9f36615&)

FLAG : 
> VishwaCTF{K3Y5_CAN_0P3N_10CK5}
