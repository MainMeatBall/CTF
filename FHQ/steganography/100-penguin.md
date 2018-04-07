# Find #30
**Description:**

***RU***
> Пингвин хочет тебе что-то сказать...

---

***ENG***
> EN: Penguin wants to tell you something...

## Writeup

This task provides PNG file with an image of a penguin.

![PNG](/FHQ/files/steganography/penguin.png)

The first thing that should be usually checked is a hex dump of any file, especially the PNG image. PNG file consists of chunks and inside every chunk it contains some data. It is possible to use command `xxd penguin.png` to get hex dump, but much simpler would be to use a hex editor, which has pre-downloaded templates and thus simplifies searching of useful information. 

![tEXt-chunk](/FHQ/images/steganography/penguin-tEXt-chunk.png)

PNG file sometimes has unnecessary chunks such as `tEXt` chunk which keeps some comments. And actually this is our case. Almost at the beginning of the file we find the `tEXt` chunk with comment `flag:{go_to_the_gym!}`.

Flag: `flag:{go_to_the_gym!}`

### Link

https://freehackquest.com/?quest=30
