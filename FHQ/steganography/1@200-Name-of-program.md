# Name of program #58
**Description:**

***ENG***
> I'm interested in the name of the program which is [hidden](/FHQ/files/steganography/name_of_program.xcf) from your eyes.

<details>
 <summary>Hint</summary>

```
Only integers, no fractions...
```
</details>

---

***RU***
> Меня интересует имя программы которое [скрыто](/FHQ/files/steganography/name_of_program.xcf) от ваших глаз.

<details>
 <summary>Подсказка</summary>

```
Кира, только целые числа никаких дробей...
```
</details>

## Writeup

We got an `XCF` file which means we should open it in GIMP. After opening, we see different layers with black background and small holes. Also they have names as numbers.

![Layers](/FHQ/images/steganography/layers-name-of-program.png)

The main layer is just a text, so maybe we should connect these holes with the text and get the answer? If you move the layer with the hole and place it before the layer with the text, you will see that it points to the certain letter. But what do these numbers in their names mean?

![text](/FHQ/images/steganography/text-name-of-program.png)

From the hint we get that there are no fractions, but what does 0,5 2,4 and 1,6 mean? But you could notice that there are eight different numbers 0 1 2 3 4 5 6 and 7, and they point to a certain letters, so maybe these numbers determine the position of the letters? If we place all letters in this order we get `man nmap`. Nmap is the short name for the program, but what is its full name? If you write in your terminal this command, you will get this important string `Nmap ("Network Mapper")` so we know that `nmap` stands for `Network Mapper` and this is our flag.

Flag: `Network Mapper`

### Link

https://freehackquest.com/?quest=58
