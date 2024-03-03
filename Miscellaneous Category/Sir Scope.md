# Miscellaneous Category:

### > Sir Scope challenge :

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194017381782126764/Screen_Shot_2024-01-08_at_9.28.43_PM.png?ex=65aed257&is=659c5d57&hm=ee50aeaa38c5bd9dcb989de315ffb844e05eef3cfea245296d4f33156eab8efb&)

in this challenge, they gave us Screenshots of [oscilloscope](https://en.wikipedia.org/wiki/Oscilloscope).

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194017381421432952/chal1.jpeg?ex=65aed257&is=659c5d57&hm=09243f110dcec1bccdb0b1d0805aafc90c0332b7a0d78382566285997813ed9e&)

in the challenge description, they told us they wrote the flag using an array of 8 LEDs, hmm... 8 LEDs so basically in binary.
I'm unfamiliar with oscilloscopes, but after examining the screenshot, I observed that in the blue line, every group of eight dots appears to be separated, indicating potentially eight LEDs. Each corresponding dot in the yellow line represents a single value, either 0 or 1.

![App Screenshot](https://cdn.discordapp.com/attachments/1067452256686981161/1194024623478677574/capture_0.jpeg?ex=65aed916&is=659c6416&hm=5dc86359aeb9ac97eb394b7ec987c2e3e174dd11267a934ea48d9ac59a72c4f5&)

Starting from right to left, in the first group, I have "01101001" which when transformed to ASCII gives me "i" the first letter in the flag format "irisctf".

Continuing this with all the remaining elements, I obtained:

"01101001 01110010 01101001 01110011 01100011 01110100 01100110 01111011 00110000 01110011 01100011 00110001 01101100 01101100 01101111 01110011 01100011 00110000 01110000 01100101 01110011 01011111 01110010 01011111 01100111 01110010 00111000 01011111 01110100 00110000 00110000 01101100 01110011 01011111 00110010 01011111 01101000 01100001 01110110 00110011 01111101"

To ASCII : 
> irisctf{0sc1llosc0pes_r_gr8_t00ls_2_hav3}
