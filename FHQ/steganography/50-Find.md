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

It is simply resolves

Flag: 

### Link

https://freehackquest.com/?quest=54
