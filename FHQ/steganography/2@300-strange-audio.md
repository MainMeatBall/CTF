# Strange audio #207
**Description:**

***ENG***

> Really? The [audio record](https://drive.google.com/open?id=1TkBdLn61hygeTEZXeCfog8MkBR5H_K7b)? Ooooh, we had an incomprehensible file at last time. Hey, you! Can you help me to figure out what's wrong?

***RU***

> Серьезно? [Аудио запись](https://drive.google.com/open?id=1TkBdLn61hygeTEZXeCfog8MkBR5H_K7b)? Оооо, нам хватило непонятного файла в прошлый раз. Эй, ты! Поможешь разобраться, что не так?

## Writeup

When you get an audio file you don't have many options. The first thing I always do is just open this file in [Audacity](https://www.audacityteam.org/download/). It is extremely helpful tool if you work with audio files. When I open a file in Audacity, I always do some simple stuff first. The first thing is to listen, the second thing is to look on number of channels, maybe to find some strange parts. Then I always check a [spectrogram](https://en.wikipedia.org/wiki/Spectrogram). For example in this file it was very simple, when I opened a spectrogram, I saw this.

![spectr1](/FHQ/images/steganography/spectro-strange-audio.png)

You can already see something strange on the right side, and when you zoom this part in, you will see this.

![flag](/FHQ/images/steganography/flag-strange-audio.png)

You can easily see that `dWdyYWN0ZntqdXN0X2Zvcl95b3V9` is base64 encoded data and after decoding you get `ugractf{just_for_you}`.

Flag: `ugractf{just_for_you}`

### Link

https://freehackquest.com/?quest=207
