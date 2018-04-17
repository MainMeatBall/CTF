# Sleep #194
**Description:**

***ENG***

> I want to [sleep](https://drive.google.com/open?id=1kyJDjQX7aSE2h7uajjYgZ6q8yf8mCe83)

***RU***

> Я хочу [спать](https://drive.google.com/open?id=1kyJDjQX7aSE2h7uajjYgZ6q8yf8mCe83)

## Writeup

We open this audio in `Audacity` and of course check the spectrogram. Seems like nothing in there but all we need to do is to ask program to show us a little bit more frequency. 

![spectro](/FHQ/images/steganography/max-freq-sleep.png)

After that we can see a text written right between ~12k and 15k frequency.

![flag](/FHQ/images/steganography/flag-sleep.png)

It is easily recognizable as base64-encoded message `RkhRKGlfbG92ZV9zbGVlcCk=` and after decoding we get `FHQ(i_love_sleep)`.

Flag: `FHQ(i_love_sleep)`

### Link

https://freehackquest.com/?quest=194
