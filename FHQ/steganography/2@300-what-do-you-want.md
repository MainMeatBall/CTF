# What do you want? #70
**Description:**

***ENG***

> What do you want from [me](/FHQ/files/steganography/What-do-you-want.png)?

***RU***

> Чего ты от [меня](/FHQ/files/steganography/What-do-you-want.png) хочешь?

## Writeup

This file is PNG so it has many different chunks and this time one of them is `tEXt` chubk with comment in it.

![hex](/FHQ/images/steganography/hex-what-do-you-want.png)

Comment says `SSB3YW50IHNsZWVwLi4uIHlvdXIgZmxhZzogMWFiMGIwMzFhODg0MWI0ODVlZDJlZGI0Yzg4M2IyNDQ=` and it is obviously a base64 encoded message. When you decode it back to text you get `I want sleep... your flag: 1ab0b031a8841b485ed2edb4c883b244` and that's it.

Flag: `1ab0b031a8841b485ed2edb4c883b244`

### Link

https://freehackquest.com/?quest=70
