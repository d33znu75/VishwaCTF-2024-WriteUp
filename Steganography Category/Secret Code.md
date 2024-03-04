# Steganography Category:

### > Secret Code challenge :

# > Description :

> Akshay has a letter for you and need your help

In this challenge, we have two attachments: a TXT file and a black picture.

Applying binwalk to the picture revealed a ZIP file containing another ZIP file, which was protected. There was also a text file stating that the password for the ZIP is a 6-digit number.

After cracking the ZIP with John using a wordlist containing all 6-digit combinations:

```
$ zip2john 5ecr3t_c0de.zip > hash
$ john --wordlist=wordlist.txt hash
```

The code was found to be 945621.

Upon extracting the ZIP, we obtained another two TXT files. One of them resembles:

```
(443, 1096)
(444, 1096)
(445, 1096)
(3220, 1096)
(3221, 1096)
(38, 1097)
(39, 1097)
(43, 1097)
(80, 1097)
(81, 1097)
(83, 1097)
(93, 1097)
(95, 1097)
...
```

And the other file suggests that these numbers might be related to the earlier image.

those are pixel cooredination so i made a pyhton script to put in those coordinations a black dot

```py
from PIL import Image, ImageDraw

def draw_points_on_blank_image(coordinates):
    width = max(coord[0] for coord in coordinates) + 10
    height = max(coord[1] for coord in coordinates) + 10

    img = Image.new("RGB", (width, height), color="white")
    draw = ImageDraw.Draw(img)

    for coord in coordinates:
        draw.point(coord, fill="black")

    img.save("image_with_points.jpg")

coordinates = [
(443, 1096),
(444, 1096),
(445, 1096),
(3220, 1096),
(3221, 1096),
(38, 1097),
(39, 1097),
(43, 1097),
(80, 1097),
(81, 1097),
(83, 1097),
(93, 1097),
...
(3221, 1166),
(3222, 1166)
]

draw_points_on_blank_image(coordinates)

print("Image created 'image_final.jpg'")

```

![](https://cdn.discordapp.com/attachments/1067452256686981161/1213953043306119168/image_with_points.jpg?ex=65f758df&is=65e4e3df&hm=3bcc249add5df7b567573e93a19ee8867886ff393cf970f84cebc9b8d9f29cf1&)

FLAG : 
> VishwaCTF{th15_15_4_5up3r_53cr3t_c0d3_u53_1t_w153ly_4nd_d0nt_5h4re_1t_w1th_4ny0ne}
