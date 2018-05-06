# Classic #165
**Description:**

***ENG***
> We like classic! `Km'x kd cneulnu, gecpnr? KZF(Vkkggjjtiuwqvqshskg)`

---

***RU***
> Нам нравится классический! `Km'x kd cneulnu, gecpnr? KZF(Vkkggjjtiuwqvqshskg)`

## Writeup

There are a few classic ciphers that you can think of, e.g. **Caesar's cipher**, **Vigener's cipher**, **Substitute cipher**. The substitute cipher would be impossible to break having such a small sentence. Also I tried all 26 rotations of Caesar's and it gave me nothing, so only Vigener is left. We need to figure out the key, so I tried to understand what was the beginning of this sentence. `Km'x` is probably `It's`, maybe there are some other options, but this one came to me in the beginning. So, we take every character of two sentences and substract ascii codes. `chr(ord('K') - ord('I') + 97)` we get `c`, and so on. From three first characters we get `ctf`. Then I know, that `KZF` should be `FHQ` and after some time I figured out the password, it was `ctfspace`. Using this password we can decipher this message and get `It's so classic, really? FHQ(Vigenereissoclassic)`.

The example of decrypting algorithm is provided.

```python
import string
s = "Km'x kd cneulnu, gecpnr? KZF(Vkkggjjtiuwqvqshskg)"

def decrypt(ciphertext, key):
    ki = 0 # key index
    si = 0 # string index
    plaintext = ''
    while si < len(s):
        if s[si] in string.ascii_letters:
            value = (ord(s[si]) - (ord(key[ki % len(key)]) - 32*s[si].isupper())) % 26
            plaintext += chr(value + 97 - 32*s[si].isupper())
            si += 1
            ki += 1
        else:
            plaintext += s[si]
            si += 1
    return plaintext

print(decrypt(s, 'ctfspace'))
```

Flag: `FHQ(Vigenereissoclassic)`

### Link

https://freehackquest.com/?quest=165
