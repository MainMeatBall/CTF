# Radiogram #120
**Description:**

***ENG***
> Can you find me? I am here, look!

---

***RU***
> Пару лет назад мы получили радиосигнал на странном языке. 
> Часть языка удалось расшифоровать, а часть так и не удалось. Помогите нам!
> Какие координаты нам были даны? 
> В наличии есть [vareq.txt](/FHQ/files/steganography/vareq.txt) и [vareq](/FHQ/files/steganography/vareq.elf) для linux

## Writeup

***ENG*** 

After reading text file and having no idea what to do with it, I opened provided ELF file in IDA Pro 7.0. The main function was very short so I looked up for other functions and found `func9(void)` in the left window with functions. It has a sequence of other functions which are just printing one character. I renamed them so it will be more comfortable to read.

![IDA_dump](/FHQ/images/steganography/IDA_dump.png)

We can see that after calling `func9()` we will see this: `key is (unknow word Marsian language) : 1,3 2,3 1,7 5,6 3,2`. And we have been asked for coordinates, so let's try them as a flag. And it worked!

Flag: `1,3 2,3 1,7 5,6 3,2`

---

***RU***

После прочтения текстового файла, я не понял, что с ним делать, поэтому открыл ELF файл в IDA Pro 7.0. Функция main была очень короткой и никуда не вела, так что я просто посмотрел на остальные функции и увидел `func9(void)` в левом окошке с функциями. В ней была последовательность других функций, которые выводили на экран по 1 символу. Для удобства, я переимновал все эти функции.

![IDA_dump](/FHQ/images/steganography/IDA_dump.png)

Таким образом, после вызова `func9()` мы увидим следующе: `key is (unknow word Marsian language) : 1,3 2,3 1,7 5,6 3,2`. И так как нас попросили узнать, какие были даны координаты, то просто попробуем сдать их как флаг. Все оказалось правильно!

Флаг: `1,3 2,3 1,7 5,6 3,2`

### Link

https://freehackquest.com/?quest=120
