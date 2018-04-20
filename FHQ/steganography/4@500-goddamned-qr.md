# Goddamned QR-code #209
**Description:**

***ENG***

> Well, after all else, [it](/FHQ/files/steganography/goddamqr.png) seems not so complicated ...

***RU***

> RU: Что ж, после всего остального, [это](/FHQ/files/steganography/goddamqr.png) кажется не таким уж и сложным...

![QR](/FHQ/files/steganography/goddamqr.png)

## Writeup

Actually, I don't know what to explain here, because this task requires only patience and nothing more. I will use GIMP to connect every QR piece. I used these three position blocks to understand the angle of the image. After some time I got this.

![qr-connected](/FHQ/images/steganography/qr-connected.png)

Then just read this qr-code and you will get something like this `1110101 1100111 1110010 1100001 1100011 1110100 1100110 1111011 1101110 1101001 1100011 1100101 1011111 1101000 1100001 1100011 1101011 1011111 1100100 1110101 1100100 1100101 1111101`. You can notice that there are several blocks, but these blocks consist of seven bits, not eight. It is strange, so let's append an additional 0 bit to the beginning of every block (the simplest method I know is to add a space at the beginning of the message and replace all spaces with zeros) and we will get this. `0111010101100111011100100110000101100011011101000110011001111011011011100110100101100011011001010101111101101000011000010110001101101011010111110110010001110101011001000110010101111101` then turn it into ascii characters and you will get the flag! 
Flag: `ugractf{nice_hack_dude}`

### Link

https://freehackquest.com/?quest=209
