# Hören Sie... #54
**Description:**

> *"Hören Sie musik und sagen Sie... Was ist das?"*  Послушайте и дайте ответ.

<details>
 <summary>Подсказка 1</summary>

```
То что вы слышите еще не ответ.
```
</details>

<details>
 <summary>Подсказка 2</summary>
  
```
Полученное слово повторите дважды (без пробелов).
```
</details>

## Writeup

We obtain this [.wav] file(../../files/steganography/Horen-sie.wav)
After listening we notice that it says `63a9f0ea7bb98050796b649e85481845`
The main point is that this string has 32 letters which is related to md5 hash.
I will use an online [service](http://md5decrypt.net/en/) to decrypt this hash.
It is decrypted ![as](/FHQ/images/steganography/Horen-Sie.png)
So, that is the flag `root`

### Link to the task

https://freehackquest.com/?quest=54
