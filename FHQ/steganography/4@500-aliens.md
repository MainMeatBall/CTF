# Aliens #34
**Description:**

***ENG***

> Let's ask the aliens? They responded with [selfie](/FHQ/files/steganography/aliens.png).

***RU***

> Спросим у инопланетян? В ответ они прислали [селфи](/FHQ/files/steganography/aliens.png).

![selfie](/FHQ/files/steganography/aliens.png)

## Writeup

One-liner solves this task easily, you just need to try different techniques and tools. Hex-editor, stegsolve, zsteg. Actually, the last one solves this task just like this: `b1,r,lsb,xy         .. text: "forget_the_gym_go_to_the_research_institute"`. The message was hidden in the last bit of the red channel.

Flag: `forget_the_gym_go_to_the_research_institute`

### Link

https://freehackquest.com/?quest=34
