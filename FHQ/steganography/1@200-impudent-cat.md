# Impudent cat #206
**Description:**

***ENG***
>  Just look what this [cat](/FHQ/files/steganography/Impudent_cat.png) is doing! Disgusting! Someone must find out what else he is up to.

---

***RU***
> Вы только посмотрите, что вытворяет этот [кот](/FHQ/files/steganography/Impudent_cat.png)! Отвратительно! Кто-то должен узнать, что еще он задумал.

## Writeup

![image-cat](/FHQ/files/steganography/Impudent_cat.png)

You can use a hex-editor or `binwalk` utility and see that this file has a rar archive after the image data. I didn't know before but actually you don't even need to extract the rar archive. It is enough to change the extension of the file to `.rar` and just open it. 

Inside you will see another image of this cat which is called `Just_fuck_your_brain.jpg`.

![Fuck_your_brain](/FHQ/files/steganography/Just_fuck_your_brain.jpg)

Nothing special about it, and the `flag.txt` file.

```
++++++++++[>+>++>+++>++++>+++++>++++++>+++++++>++++++++>++++++++
+>++++++++++>+++++++++++>++++++++++++>+++++++++++++<<<<<<<<<<<<<
-]>>>>>>>>>>>>---.<-------.>---.<<---.++.>>++.<-.>>-------.<<<<<
<<<-.>>>>>>>.<<----.<<-------.>>>>-.<<.>>.<<<<++++++.>>.>>.<<<<<
<<.>>>>>>+++++++.>---.<-.<<<<<---------.>>>>>>>++.
```

If you trained to solve CTF tasks before, you would know of this language, because it is the most popular esoteric language in CTF. It is called `brainfuck`, you can [read](https://en.wikipedia.org/wiki/Brainfuck) about it if you want to. Actually, the name of the image inside this archive also provided a hint. This language has many interpreters online and I will use [this one](https://copy.sh/brainfuck/) to decode our message. We load our brainfuck code and click `run` button and we see the message `ugractf{1t_Is_sO_s1mpl3}`. That's it, very simple.



Flag: `ugractf{1t_Is_sO_s1mpl3}`

### Link

https://freehackquest.com/?quest=206
