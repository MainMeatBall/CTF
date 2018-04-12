# Something inside #205
**Description:**

***ENG***
> Someone left this [file](https://drive.google.com/open?id=1AbMJIz5wBxKNFs0i_4rXnxky8upufArf) on our server. Can you find out, what is inside?

<details>
 <summary>Hint 1</summary>

```
Is it image?
```
</details>

<details>
 <summary>Hint 2</summary>

```
What do you know about the channels of image?
```
</details>

---

***RU***
> Кто-то оставил этот [файл](https://drive.google.com/open?id=1AbMJIz5wBxKNFs0i_4rXnxky8upufArf) на нашем сервере. Можешь посмотреть, что в нем? 

<details>
 <summary>Подсказка 1</summary>

```
Может быть это изображение?
```
</details>

<details>
 <summary>Подсказка 2</summary>

```
Что вы знаете о каналах изображения?
```
</details>

## Writeup

After downloading this archive we can try to unpack it, but it is impossible. `Wrong.rar is not RAR archive. No files to extract` is says. What is it then? Let's use `file` utility on this file and we will find out that it is a `Wrong.rar: PNG image data, 1920 x 1080, 8-bit/color RGBA, interlaced`. Just change the extension from `.rar` to `.png` and you will have this image.

![Wrong-image](/FHQ/images/steganography/Wrong.png)

Seems that nothing wrong with it at first sight and in hex-editor so we will use a very powerful tool in steganography -- `stegsolve`. If nothing is wrong with image at first sight then hidden data would be probably hiding in LSB. And if we check one of the RGB channels, for example red one, we will see this.

![Wrong-stegsolve](/FHQ/images/steganography/Wrong-stegsolve.png)

Flag: `ugractf{1s_th4t_34sy_f0r_y0u?}`

### Link

https://freehackquest.com/?quest=205
