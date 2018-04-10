# Remastered #140
**Description:**

***ENG***
> [It speaks](https://drive.google.com/open?id=1WBIzRLDu4jv6IrX8683A7DCAX4CHxVNA)! Not quite sure what it's saying though... 

---

***RU***
> [Оно разговаривает](https://drive.google.com/open?id=1WBIzRLDu4jv6IrX8683A7DCAX4CHxVNA)! Хотя я не совсем уверен, что оно говорит... 

## Writeup

These sounds reminded me of R2-D2 from Star Wars, but I found nothing interesting there. But if you open this audio file in a program like `Audacity`, you can see that this file has eight channels. You can also look in hex-editor and confirm that information. It is actually very strange and very suspicious, why eight? When you meet a WAV file in steganography it usually has hidden data as LSB (Least Significant Bit), or maybe if it has two channels the data coukd be hiding as a difference between them, but this one has eight channels. So the first idea that came to my mind reffered to number eight and LSB that one byte consists of eight bits. Maybe I should try to take one bit from every channel and connect them into one byte? In 16-bit wav files data bytes are following each other in this order: 2 bytes of first channel, 2 bytes of second channel, ... 2 bytes of last channel. So I will use python to get them.

```python
wr = open("/Users/Meatball/FHQ/Remastered_decoded", "wb")

byte = [0]*8

with open("/Users/Meatball/FHQ/Remastered.wav", "rb") as f:
    header = f.read(44)
    for _ in range(8000):

        for i in range(8):
            byte[i] = int.from_bytes(f.read(2), byteorder='little') & 1

        stro = (''.join(str(ch) for ch in byte))[::-1]
        wr.write(int(stro, 2).to_bytes((len(stro) + 7) // 8, 'big'))

wr.close()

```

Actually, first of all I tried to take those bits in big-endian order but that gave me nothing. So thought that reverse that order would be worth trying. And it was.

Then you can use `file` utility or just open in hex-editor and see that it is a PNG image. 

```
Remastered_decoded: PNG image data, 1024 x 1024, 8-bit/color RGB, non-interlaced
```

So we just change the extension of the file to `.png` and open it.

![image](/FHQ/images/steganography/remastered.png)

Flag: `VolgaCTF{th3re_@re_eight_bits_in_@_byt3}`

### Link

https://freehackquest.com/?quest=140
