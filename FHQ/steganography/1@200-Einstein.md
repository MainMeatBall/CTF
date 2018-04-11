# Einstein #31
**Description:**

***ENG***
>  [Einstein](https://drive.google.com/open?id=1p21a17ThO7f9ED4citmAJB2kOkGQTq6_) expressed his opinion about the statements of the Penguin...

---

***RU***
> [Эйнштейн](https://drive.google.com/open?id=1p21a17ThO7f9ED4citmAJB2kOkGQTq6_) высказал свое мнение по поводу высказывания Пингвина...

## Writeup

We got an `XCF` file which means we should open it in GIMP. After opening, we see different layers with colored data.

![Layers](/FHQ/images/steganography/Layers-Einstein.png)

If we combine all pieces in one image, we will understand that this is a qr-code because of the position blocks.

![Combined-qr](/FHQ/images/steganography/Combined-qr-Einstein.png)

So after some manipulations in GIMP and using `inverse brightness` we got this image.

![Fixed-qr](/FHQ/images/steganography/QREinstein.png)

Read it with your mobile device or online and you will get the message `i_agree_to_the_penguin`.

Flag: `i_agree_to_the_penguin`

### Link

https://freehackquest.com/?quest=31
