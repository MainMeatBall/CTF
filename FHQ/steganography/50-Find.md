# Find #180
**Description:**

***RU***
> Вы сможете меня найти? Смотри, я здесь!

---

***ENG***
> Can you find me? I am here, look!

## Writeup

We get this [archive](/FHQ/files/steganography/GameCTF.tar.gz) file.

To extract files from `.tar.gz` archive we will use `tar -xf GameCTF.tar.gz`. We extracted GameCTF folder with game and other files. It is unnessesary to play the game so let's try to find something interesting inside `SpaceCTFGame_Data` folder instead. After some research we find `Background.jpg` in `Resourses`. 

![image](/FHQ/images/steganography/Find-backgroud.jpg)

It is simply resolves as morse code, which we can rewrite like this: `__. ___ ___ _.. __..__ _..._ .._. ._.. ._ __. _..._ .. ... _..._ .. _._. ._ _. ... . . .. _` so we can use it for decryption. I will use this online morse code [translator](https://morsecode.scphillips.com/translator.html), which will provide this information.

![image](/FHQ/images/steganography/Find-morse-decryption.png)

Actually, `_..._` is an equal sign `=` so it was used here to immitate spaces, but probably this decoder is'n sure what did we mean by `_..._` so it decoded it like `<BT>`.

Flag: `ICANSEEIT`

### Link

https://freehackquest.com/?quest=180
