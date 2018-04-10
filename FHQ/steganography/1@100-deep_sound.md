# deep_sound #110
**Description:**

***ENG***
> One of our employees decided to check the qualification of our personal nowadays and sent us [this file](https://drive.google.com/open?id=1u6c4l1wKBkn28yHvOkcQRQ65i4TupIAv). But any of our agents couldn't find anything. Help us, please!

---

***RU***
> Один из наших бывших сотрудников решил проверить, насколько квалифицированные специалисты работают сейчас тут, и прислал нам [этот файл](https://drive.google.com/open?id=1u6c4l1wKBkn28yHvOkcQRQ65i4TupIAv). Но ни один из наших агентов не смог ничего найти. Пожалуйста, помогите нам!

## Writeup

***ENG***

This task provides [.wav](https://drive.google.com/open?id=1u6c4l1wKBkn28yHvOkcQRQ65i4TupIAv) file.

We can listen to this wav file and hear nothing suspicious. However, if you play CTF, you know that task names can provide some useful information. This task is a good example. `DeepSound` is a steganography tool which is used for hiding secret data into audio files.

![screenshot_winXP](/FHQ/images/steganography/deep_sound.png)

The moment I opened `deep_sound.wav` in `DeepSound` it showed me that this audio contains a secret image file `stego.jpg`. So let's extract it by pushing `Extract secret files` button and then open the image.

![stego](/FHQ/files/steganography/deep_sound-stego.jpg)

Nothing seems very strange about it so I'm going to open it in hex editor. According to JPEG file structure the last two bytes are always `0xFFD9` so very often in tasks you can find some data right after image data. This task is not an exception and we find `Rar` archive there.

![RarHex](/FHQ/images/steganography/deep_sound-hex.png)

I will use the `dd` utilite to cut out archive from image using the information from hex editor like offset and length: `dd if=deep_sound-stego.jpg of=flag.rar skip=0x15338 bs=1 count=105`. And the last step is open this archive `unrar x flag.rar` and read the file. `cat 2.txt` provided this output: `flag: it's_easy_breasy_steganography`.

The other solution was to use `binwalk` utility. It gives us this information:

```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
86840         0x15338         RAR archive data, first volume type: MAIN_HEAD
```

And after that we just extract data like `binwalk -e deep_sound-stego.jpg`.

Actually you could see that flag back in hex editor because rar couldn't compress this text file, but nevertheless we did everything till the end.

Flag: `it's_easy_breasy_steganography`

---

***RU***

В этом задании мы скачиваем [аудио файл](https://drive.google.com/open?id=1u6c4l1wKBkn28yHvOkcQRQ65i4TupIAv).

Можно прослушать этот файл и не услышать ничего подозрительного. Однако, если вы знакомы с CTF, то должны знать, что в названии заданий может присутствовать полезная информация или даже подсказка. Это задание как раз таким и является. `DeepSound` это утилита для стеганографии, которая используется для скрытия секретной информации в аудио файлы.

![screenshot_winXP](/FHQ/images/steganography/deep_sound.png)

Как только я открыл `deep_sound.wav` в `DeepSound`, программа мне показала, что этот файл содержит секретное изображение `stego.jpg`. Давайте извлечем его, нажав на `Extract secret files` и затем откроем изображение.

![stego](/FHQ/files/steganography/deep_sound-stego.jpg)

На картинке не изображено ничего странного, так что откроем его в hex-редакторе. Зная, что у формата JPEG последние два байта всегда `0xFFD9`, можно часто встретить допольнительную информацию, которая идет сразу после этих байтов. Это задание не исключение и мы находим там `Rar` архив.

![RarHex](/FHQ/images/steganography/deep_sound-hex.png)

Я исполльзую утилиту `dd`, чтобы вынуть архив из изображения, зная каков сдвиг и его размер из hex-редактора: `dd if=deep_sound-stego.jpg of=flag.rar skip=0x15338 bs=1 count=105`. И последний шаг это распаковать архив `unrar x flag.rar` и прочитать файл. `cat 2.txt` предоставляет следующий текст: `flag: it's_easy_breasy_steganography`.

Еще один удобный вариант -- это использовать утилиту `binwalk` на изображении, которая предоставит такую информацию:

```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.01
86840         0x15338         RAR archive data, first volume type: MAIN_HEAD
```

После чего просто извлечем данные командой `binwalk -e deep_sound-stego.jpg`.

На самом деле, открыв изображение в hex-редакторе уже можно было увидеть флаг, так как скорее всего архиватор не смог ничего сжать, но мы все равно проделали задание до конца.

Флаг: `it's_easy_breasy_steganography`

### Link

https://freehackquest.com/?quest=110
