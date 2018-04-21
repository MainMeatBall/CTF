# abcdefgh #174
**Description:**

***ENG***
> We intercepted the encrypted message. Decrypt it!

`bac bai jh bad bcd gf bbf jj ej ej jf hh jh bbf bbg fb ic bcf`

---

***RU***
> Мы перехватили зашифрованное сообщение. Расшифруй его!

`bac bai jh bad bcd gf bbf jj ej ej jf hh jh bbf bbg fb ic bcf`

## Writeup

The name of the task gives us a clue and we see that there is no letter in intercepted message greater then `j`. Actually, there are only ten different letters as ten digits exist in our world. So, if we match every letter in this message to 0-9 digits, we will probably decrypt it. Let's try with one-liner in python:

```python
flag = "".join(chr(int(i)) for i in "".join(str("abcdefghij".find(ch)) if ch is not ' ' else ' ' for ch in "bac bai jh bad bcd gf bbf jj ej ej jf hh jh bbf bbg fb ic bcf").split(' '))
```

Flag: `flag{Asc11_Mast3R}`

### Link

https://freehackquest.com/?quest=174
