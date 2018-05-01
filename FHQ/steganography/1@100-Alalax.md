# Alalax #191
**Description:**

***ENG***
> Intercepted a strange [file](/FHQ/files/steganography/alalax.xcf).

---

***RU***
> Перехватили странный [файл](/FHQ/files/steganography/alalax.xcf).

## Writeup

So let's start from identifying the `XCF` extension by using `file` or just googling. If we use `file` utility, we will get `alalax.xcf: GIMP XCF image data, version 0, 350 x 325, RGB Color`. And if we google it, we will get pretty much the same infromation about GIMP file. So if you don't have GIMP you should download it and if you have one, just let's open this file in there. 

We will see a QR-code but you will not be able to read it because of inverted colors. After inverting colors we get this picture.

![QRcode](/FHQ/images/steganography/QRalalax.png)

Which provided this information inside `60, there's n0thin6 interestin6`. There is nothing interesting... But why `XCF` extension, why not just `JPG` or `PNG`? The main property of GIMP or PSD files is that we can store layers there.

![Layers](/FHQ/images/steganography/alalaxLayers.png)

We can see the second layer with strange image.

![maxicode](/FHQ/images/steganography/alalaxmaxi.png)

If you google it, or if you just know, you will easily recognize a `MaxiCode`. I will decode this code using this [online service](https://zxing.org/w/decode.jspx) and will get this message `FHQ(alalax_is_just_delirium)`.

Flag: `FHQ(alalax_is_just_delirium)`

### Link

https://freehackquest.com/?quest=191
