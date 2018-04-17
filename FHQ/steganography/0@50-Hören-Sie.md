# Hören Sie... #54
**Description:**

***ENG***
> *"Hören Sie musik und sagen Sie... Was ist das?"*  [Listen](/FHQ/files/steganography/Horen-sie.wav) and give the answer. The obtained word repeat twice without spaces.

<details>
 <summary>Hint</summary>

```
What you hear is not an answer yet.
```
</details>

---

***RU***
> *"Hören Sie musik und sagen Sie... Was ist das?"*  [Послушайте](/FHQ/files/steganography/Horen-sie.wav) и дайте ответ. Полученное слово повторите дважды без пробелов.

<details>
 <summary>Подсказка</summary>

```
То, что вы слышите, еще не ответ.
```
</details>

## Writeup

Let's just listen to the audio. Some letters and digits are being said and after writing them down, we have `63a9f0ea7bb98050796b649e85481845`. The main point is that this string has 32 letters which reminds of `md5`. I will use an online [service](http://md5decrypt.net/en/) to decrypt this hash.

![image](/FHQ/images/steganography/Horen-Sie.png)

The description above is asking to repeat this word twice without spaces, and we will take this advice.

Flag: `rootroot`

### Link

https://freehackquest.com/?quest=54
