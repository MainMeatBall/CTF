# Caesar again #9
**Description:**

***ENG***
> Again another [Caesar](/FHQ/files/cryptography/caesar.txt).

---

***RU***
> Еще один [Цезарь](/FHQ/files/cryptography/caesar.txt).

## Writeup

I want to say it in the very beginning that Caesar has nothing to do with this task and I have no idea why it has been named like this. This is a permutation cipher which could be solved using frequency analysis and then finding some recognizable patterns of words. I will use [CyberChef](https://gchq.github.io/CyberChef/) because it is extremely convenient. We choose the `Substitute` recipe and then write this piece of code to find out the most frequent letters in this text. The text is already lowercased, I did it in text editor. 

```python
from collections import Counter
from string import ascii_lowercase

with open('/Users/Meatball/FHQ/caesar.txt') as f:
	text = f.read()
	c = Counter(text)
	print("".join(i[0] if i[0] in ascii_lowercase else '' for i in c.most_common()))
```

It gives us `jpkrvmtywdqgusfbhecanilxzo`. Then we google the most frequent characters in english language and it is `etaoinshrdlcumwfgypbvkjxqz`.

![frequency](/FHQ/images/cryptography/frequency.png)

We fill the plaintext and ciphertext in this substitute recipe with these strings and we will get a little bit more understandable text. For example I found this piece near the end of the text `io deleuben 19` and I assumed that it means `on december 19` really, so we will change the ciphertext a bit, and actually you will see that you will need just to swap some adjacent pairs of letters and you will get the original text about chevrolet camaro. But there is no flag!

Sometimes you need to reveal what was the key for your substitution cipher, for example it the end we will see that we will have `eatnorishdclmupgfwvbykzxjq` ciphertext. Maybe we will need to sort it properly and it will be the flag? Let's try. 

```python
s1 = 'eatnorishdclmupgfwvbykzxjq'
s2 = 'jpkrvmtywdqgusfbhecanilxzo'
a = "".join(i[1] for i in sorted(zip(s1,s2), key=lambda x: x[0]))
```

Flag: `paqdjhbwtzigurvfomykscexnl`

### Link

https://freehackquest.com/?quest=9
