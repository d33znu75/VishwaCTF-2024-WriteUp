### > Repo Riddles challenge :

# > Description :

> We got a suspicious Linkedin post which got a description and also a zip file with it. It is suspected that a message is hidden in there. Can you find it?

>LinkedIn Post Description:

>Title: My First Project -The Journey Begins

>Hello fellow developers and curious minds!

>I'm thrilled to share with you my very first Git project - a labor of love, dedication, and countless late-night commits. 🚀

>Explore the code, unearth its nuances, and let me know your thoughts. Your feedback is invaluable and will contribute to the ongoing evolution of this project.


We had an attachment containing a zip file. Upon extracting the zip file, I executed the command "ls -a" and found a directory named ".git". To explore further, I used the command "git reflogs" to inspect the commit history.

While browsing through the commit history, I stumbled upon a text file containing flag characters and their corresponding indices. Additionally, within the commit history, there was a commit that has a Spotify web page and in its source code we have another flag characters. Furthermore, an image was also discovered in the commit history.

By combining these findings , I was able to get the flag.

string[9] = _
string[10] = 2
string[11] = 7
string[12] = 2
string[13] = 7

string[3: 6] = G1g

string[0] = G string[1] = 1 string[2] = t

![](https://cdn.discordapp.xyz/attachments/1067452256686981161/1213925109228638368/Screen_Shot_2024-03-03_at_8.04.48_PM.png)


Flag:
> VishwaCTF{G1t_G1gger_2727}
