# Box of cats #208
**Description:**

***ENG***

> Aww~ These are cats! A whole [box of cats](https://drive.google.com/open?id=1r0ik9WdyMWu3tYi5af5LqY7TCk_0Rl9Y). Bring me a duck tape, my face is cracking of cuteness.

***RU***

> Оуу~ Это котики! Целая [коробка котиков](https://drive.google.com/open?id=1r0ik9WdyMWu3tYi5af5LqY7TCk_0Rl9Y). Несите скотч, у меня лицо трескается от умиления.

## Writeup

After unpacking this rar archive, we can see 20 picures of cats and one "important" image.

![important](/FHQ/images/steganoghraphy/important.png)

We see a lot of zeros, and if we won't be lazy and count them, we will see that there are 32 of them. Number 32 always reminds me of md5, so maybe something is connected with it? We notice that the tvelfth digit is marked with a blue color. I suppose that the meaning of it is to show that the 12th sybmol is important for us. Let's bring it all together: md5 is 32 symbols long and we need to pay attention at 12th character.

We have 20 images of cats and it is well known fact that you can count md5 from a file, so let's do that. But before delete this `important.png` file. I will use just my command line `md5sum $(ls | sort -n) | cut -c 12 | tr -d '\n'`, where `ls | sort -n` stands for sorting items due to names, `cut -c 12` means that we take only 12th character out of a string and `tr -d '\n'` deletes every newline so we can use our output. After all manipulations we got `666c756666795f636174` which is of course hex-encoded message and after decoding we get `fluffy_cat`. To decode we could easily append `xxd -r -p` through the pipe to our md5 command string.

Flag: `fluffy_cat`

### Link

https://freehackquest.com/?quest=208
