# Big_data #97
**Description:**

***ENG***
> One crazy mathematician sent [this](https://drive.google.com/open?id=1Rcen5GJ0t-mdKfB-_GmlBuiJAmXOFiwR) to us.

---

***RU***
> Один сумасшедший математик прислал нам [это](https://drive.google.com/open?id=1Rcen5GJ0t-mdKfB-_GmlBuiJAmXOFiwR).

## Writeup

Seems as a pretty simple task, but if you will try to do it on python without any modules and using just `int()` type cast, you will fail, because the precision in incorrect. There are some huge numbers in this text document, so it is necessary to use for example `decimal` module and set some precision.

```python
from decimal import Decimal, getcontext
getcontext().prec = 10000
with open('big_data.txt') as f:
    nums = sum([Decimal(i) for i in f.read().split()])
```

We get `nums = 101101001101101011110000110100001011010001100100110110001111010010100010110101101101100010010000101101001000111010001100011000001011001010101010110110001010100010110010011001000111001011101100110001001000011010001010011110100001010` and treating it like binary, we get `5a6d78685a326c7a516b6c485a47463059556c54593239766243453d0a` number in hex. It is not difficult to notice that it seems like hex numbers of ascii symbols. Let's convert this number to letters and we will get `ZmxhZ2lzQklHZGF0YUlTY29vbCE=` that is base64. And the base64-encrypted text is `flagisBIGdataIScool!`

Flag: `BIGdataIScool!`

### Link

https://freehackquest.com/?quest=97
