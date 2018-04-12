# texts #111
**Description:**

***ENG***
> It is known that in digital civilization all main communications are provided in binary code form. But imperfect biological creatures are immune to perception of this pure and absolute form of information. Thus old-fashioned symbols haven't still extinct. However are symbols always specify something that seems right on the first sight? Flag format: MIK_*

---

***RU***
> Как известно, в цифровой цивилизации все основные коммуникации ведутся в форме двоичных кодов. Но несовершенные биологические создания не способны к восприятию данной чистой и совершенной формы информации. Поэтому устаревшие символы ещё не вымерли. Однако всегда ли символы обозначают то, что кажется на первый взгляд? Формат флага: MIK_*

Task: RE==b9==IE==eZ==b0==db==IF==cv==ZW==YS==bG==bB==eX==ID==dG==aF==aT==bm==az==LE==IF==dP==aG==Yd==dG==IJ==dG==aH==aW==c4==IH==Yk==YV==c/==ZW==Nj==NG==IP==Y2==b+==bn==dE==YW==aR==bm==c5==IG==ee==b1==df==cm==IF==Zn==bI==YX==Z0==P3==IC==TW==YR==eV==IP==Ym==ZY==IG==eZ==b2==dU==IG==Y0==YW==bl==IG==c+==ZV==Yf==cm==Y5==aG==IO==aW==dG==IG==c/==b3==bS==ZW==d9==aG==ZR==cn==ZU==IG==ZZ==bG==c/==ZW==Ie==

## Writeup

Obviously everyone would mention that it is base64-encoded information and first of all we can try to decode it. And we obtain this message `Do you really think, that this base64 contains your flag? May be you can search it somewhere else!`. Hmm, no flag in this message? But this task gave us only this base64 string, nothig else. 

Yes, that's right. Let's remember the inner structure of base64 encoding. I think the table from [wikipedia](https://en.wikipedia.org/wiki/Base64) is very sufficient for this.

![base64](/FHQ/images/steganography/base64-texts.png)

For every three symbols 8 bits each in original data we got 4 symbols 6 bits each of base64-encoded data. 6 bits means number not greater then 63 so that means 64 different numbers zero included. And we have a special base64 alphabet which looks like `ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/`. That is so simple!

Thus we use blocks of three letters each to encrypt it to base64, but what happens if we got for example block of one single letter? We would use `=` sign at the end of the block to fill the last block so it would have 4 symbols instead of two.

Now we can see the main point of this task. Let's take first block `RE==`, so we have R = 6 bit, E = 6 bit and 12 bit at the end for padding. If we translate it back to original text, we would have only one letter `D`. That is just 8 bits. And now you realize that we don't use the last 4 bits of this block. We could change letter `E (000100) <- base64 binary code` to letter with any 4 last bytes, it doesn't matter, for example letter O (001111) and decipher `RO==` back to normal text. Nothing changed, same letter `D`. 

So we can actually store data inside those 4 last bits of each block and hide it in another normal message. I will use python to take out those 4 bits of each block and transform it to text.

```python
import re

b64alphabet = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/'

s = 'RE==b9==IE==eZ==b0==db==IF==cv==ZW==YS==bG==bB==eX==ID==dG==aF==aT==bm==az==LE==IF==dP==aG==Yd==dG==IJ== dG==aH==aW==c4==IH==Yk==YV==c/==ZW==Nj==NG==IP==Y2==b+==bn==dE==YW==aR==bm==c5==IG==ee==b1==df==cm==IF== Zn==bI==YX==Z0==P3==IC==TW==YR==eV==IP==Ym==ZY==IG==eZ==b2==dU==IG==Y0==YW==bl==IG==c+==ZV==Yf==cm==Y5== aG==IO==aW==dG==IG==c/==b3==bS==ZW==d9==aG==ZR==cn==ZU==IG==ZZ==bG==c/==ZW==Ie=='

a = re.findall(r'..==', s)
s = ''
for i in a:
    s += '{0:08b}'.format(b64alphabet.find(i[1]))[4::]
n = int(s, 2)
a = n.to_bytes((n.bit_length() + 7) // 8, 'big').decode('utf-8')
print(a)
```

And it prints out `MIK_base64_might_contain_extra_hidden_information`

Flag: `MIK_base64_might_contain_extra_hidden_information`

### Link

https://freehackquest.com/?quest=111
