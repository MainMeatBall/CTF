# Find #180
**Description:**

***ENG***
> Can you find me? I am [here](https://drive.google.com/open?id=13dWOFCkDnF2J_S5NRddgvCvqQK7tmdzZ), look!

---

***RU***
> Вы сможете меня найти? Смотри, я [здесь](https://drive.google.com/open?id=13dWOFCkDnF2J_S5NRddgvCvqQK7tmdzZ)!

## Writeup

***ENG*** 

We get this [archive](https://drive.google.com/open?id=13dWOFCkDnF2J_S5NRddgvCvqQK7tmdzZ) file.

To extract files from `.tar.gz` archive we will use `tar -xf GameCTF.tar.gz`. We extracted `GameCTF` folder with game and other files. It is unnessesary to play the game so let's try to find something interesting inside `SpaceCTFGame_Data` folder instead. After some research we find `Background.jpg` in `Resourses`. 

![image](/FHQ/images/steganography/Find-backgroud.jpg)

It is simply resolves as morse code, which we can rewrite like this: `__. ___ ___ _.. __..__ _..._ .._. ._.. ._ __. _..._ .. ... _..._ .. _._. ._ _. ... . . .. _` so we can use it for decryption. I will use this online morse code [translator](https://morsecode.scphillips.com/translator.html), which will provide this information.

![image](/FHQ/images/steganography/Find-morse-decryption.png)

Actually, `_..._` is an equal sign `=` and `BT , New paragraph` so it was used here to imitate `space` character.

Flag: `ICANSEEIT`

---

***RU***

Мы получаем такой [архив](https://drive.google.com/open?id=13dWOFCkDnF2J_S5NRddgvCvqQK7tmdzZ).

Чтобы извлечь файлы из архива с раширением `.tar.gz` мы используем следующую команду `tar -xf GameCTF.tar.gz`. Мы извлекли `GameCTF` папку с игрой и какими-то файлами. Играть в игру совсем не обязательно, так что лучше попробовать найти что-то интересное в папке `SpaceCTFGame_Data`. Немного поискав, находим `Background.jpg` в папке `Resourses`. 

![image](/FHQ/images/steganography/Find-backgroud.jpg)

Не долго думая, понимаем, что это азбука Морзе, которую для удобства расшифровки перепишем в текст: `__. ___ ___ _.. __..__ _..._ .._. ._.. ._ __. _..._ .. ... _..._ .. _._. ._ _. ... . . .. _`. Я использую [онлайн-переводчик](https://morsecode.scphillips.com/translator.html) азбуки Морзе, который предоставит следующую информацию.

![image](/FHQ/images/steganography/Find-morse-decryption.png)

На самом деле, `_..._` это знак "равно" `=` и `BT , New paragraph` так что он был использован в данном сообщении вместо пробела.

Флаг: `ICANSEEIT`

### Link

https://freehackquest.com/?quest=180
