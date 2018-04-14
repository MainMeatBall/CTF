# designer #192
**Description:**

***ENG***
> I always wanted to code websites, but sometimes something didn't work. [Help me](/FHQ/files/steganography/designer.zip)! The answer is only in lowercase.

---

***RU***
> Я всегда хотел хорошо верстать сайты, но иногда что-то не получалось. [Помогите мне](/FHQ/files/steganography/designer.zip). Ответ дайте в нижнем регистре.

## Writeup

After unzipping the archive we got the image that just being used in html file. Let's open this `index.html` in Google Chrome browser as it is the most comfortable browser for using developers tools. 

![Chrome](/FHQ/images/steganography/chrome-designer.png)

We actually see that there are 10 figures and we see only the figure #6. What happened to the others? Actually, it is rather simple, and after you open this file in a text editor, you will see everything. 

As we open this file, we can see that there are a lot of css selectors and we can find `#symbols` ones that we need. Every figure consists of two red smaller simple figures which are written here as `#f:before` and `#f:after`. Everything is fine until we notice that after 10th figure there are `#sybmols` selectors again starts with figure 1. 

![Sublime](/FHQ/images/steganography/sublime-designer.png)

In CSS if you write the same selector twice it won't complain. It will just owerwrite it and forget about the first one. So maybe everything is broken because of them? Let's try to remove them, save and open this file in web browser again.

![Sublime](/FHQ/images/steganography/flag-designer.png)

As we were asked to write this flag in lowercase, we will do so.

Flag: `FHQ(ilovectf)`

### Link

https://freehackquest.com/?quest=192
