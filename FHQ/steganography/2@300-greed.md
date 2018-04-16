# greed #193
**Description:**

***ENG***

> Someone hid an information in the [picture](/FHQ/files/steganography/greed.png).

***RU***

> Кто-то спрятал в [картинке](/FHQ/files/steganography/greed.png)информацию.

![greed](/FHQ/files/steganography/greed.png)

## Writeup

Actually, I have no idea what to say about this task because you can solve it in one move. It is a classic LSB method in PNG and there are many tools to see that. First of all I checked this image in hex-editor and saw nothing. Then I decided to check this image for LSB and used  a very comfortable tool [zsteg](https://github.com/zed-0xff/zsteg). The usage is very simple, and it gives you the answer just like that.

![zsteg](/FHQ/images/steganography/zsteg-greed.png)

You can have the same result in a tool called [stegolve](https://github.com/zardus/ctf-tools/tree/master/stegsolve). It is a tool number one, but this time I preffered another one. Nevertheless, you can solve this task with `stegsolve` like this

![stegsolve](/FHQ/images/steganography/stegsolve-greed.png)

Flag: `FHQ(lsbisaclassicforsteganography)`

### Link

https://freehackquest.com/?quest=193
