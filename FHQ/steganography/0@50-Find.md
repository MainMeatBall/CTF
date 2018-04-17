# Find #180
**Description:**

***ENG***
> Can you find me? I am [here](https://drive.google.com/open?id=13dWOFCkDnF2J_S5NRddgvCvqQK7tmdzZ), look!

---

***RU***
> Вы сможете меня найти? Смотри, я [здесь](https://drive.google.com/open?id=13dWOFCkDnF2J_S5NRddgvCvqQK7tmdzZ)!

## Writeup

To extract files from `.tar.gz` archive we will use `tar -xf GameCTF.tar.gz`. We extracted `GameCTF` folder with the game and other files. It is unnessesary to play the game, so let's try to find something interesting inside `SpaceCTFGame_Data` folder instead. After some research, we find `Background.jpg` in `Resourses`. 

![image](/FHQ/images/steganography/Find-backgroud.jpg)

It simply resolves as Morse code, which we can rewrite like this: `__. ___ ___ _.. __..__ _..._ .._. ._.. ._ __. _..._ .. ... _..._ .. _._. ._ _. ... . . .. _`, now we can use it for decryption. I will use this online Morse code [translator](https://morsecode.scphillips.com/translator.html), which will provide this information.

![image](/FHQ/images/steganography/Find-morse-decryption.png)

Actually, `_..._` is both an equal sign `=` and `BT , New paragraph` so it was used here to imitate `space` character.

Flag: `ICANSEEIT`

### Link

https://freehackquest.com/?quest=180
