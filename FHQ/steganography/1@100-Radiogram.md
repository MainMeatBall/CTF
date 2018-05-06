# Radiogram #120
**Description:**

***ENG***
> A couple of years ago we recieved a radiosignal on a strange language. We were able to decrypt only a part of this language. Help us! What coordinates did we recieve? We have these [vareq.txt](/FHQ/files/steganography/vareq.txt) and [vareq](/FHQ/files/steganography/vareq.elf) for linux.

---

***RU***
> Пару лет назад мы получили радиосигнал на странном языке. Часть языка удалось расшифоровать, а часть так и не удалось. Помогите нам! Какие координаты нам были даны? В наличии есть [vareq.txt](/FHQ/files/steganography/vareq.txt) и [vareq](/FHQ/files/steganography/vareq.elf) для linux.

## Writeup

After reading the text file and having no idea what to do with it, I opened provided ELF file in IDA Pro 7.0. The main function was very short so I looked up for other functions and found `func9(void)` in the left window with functions. It had a sequence of other functions which were just printing one character. I renamed them so it would be more comfortable to read.

![IDA_dump](/FHQ/images/steganography/IDA_dump.png)

We can see that after calling `func9()` we will see this: `key is (unknow word Marsian language) : 1,3 2,3 1,7 5,6 3,2`. And we have been asked for coordinates, so let's try them as a flag. And it worked!

Flag: `1,3 2,3 1,7 5,6 3,2`

### Link

https://freehackquest.com/?quest=120
