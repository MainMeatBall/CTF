# Penguin #30
**Description:**

***RU***
> [Пингвин](/FHQ/files/steganography/penguin.png) хочет тебе что-то сказать...

---

***ENG***
> [Penguin](/FHQ/files/steganography/penguin.png) wants to tell you something...

## Writeup

***ENG***

This task provides PNG file with an image of a penguin.

![PNG](/FHQ/files/steganography/penguin.png)

The first thing that should be usually checked is a hex dump of any file, especially the PNG image. PNG file consists of chunks and inside every chunk it contains some data. It is possible to use command `xxd penguin.png` to get hex dump, but much simpler would be to use a hex editor, which has pre-downloaded templates and thus simplifies searching of useful information. 

![tEXt-chunk](/FHQ/images/steganography/penguin-tEXt-chunk.png)

PNG file sometimes has unnecessary chunks such as `tEXt` chunk which keeps some comments. And actually this is our case. Almost at the beginning of the file we find the `tEXt` chunk with comment `flag:{go_to_the_gym!}`.

Flag: `flag:{go_to_the_gym!}`

---

***RU***

В этом задании мы получаем изображение пингвина.

![PNG](/FHQ/files/steganography/penguin.png)

Первым делом стоит проверить hex-дамп файла, особенно если это PNG изображение. PNG состоит из нескольких чанков и внутри каждого чанка он содержит какие-то данные. Чтобы получить hex-дамп файла можно использовать команду `xxd penguin.png`, но намного проще будет использовать hex-редактор, в котором есть готовые шаблоны, которые упростят поиск нужной информации.

![tEXt-chunk](/FHQ/images/steganography/penguin-tEXt-chunk.png)

PNG изображение иногда содержит необязательные чанки, например `tEXt`, в котором содержатся какие-либо комментарии. И в этом задании как раз практически в начале файла мы видим этот `tEXt` чанк с комментарием `flag:{go_to_the_gym!}`.

Флаг: `flag:{go_to_the_gym!}`

### Link

https://freehackquest.com/?quest=30
