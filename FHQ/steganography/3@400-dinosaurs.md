# dinosaurs #33
**Description:**

***ENG***

> What did dinosaurs [reply](https://drive.google.com/open?id=1a_ufNxMR8rIWjbZGo3tk0GokfjnWfp2R)?

***RU***

> Что [ответили](https://drive.google.com/open?id=1a_ufNxMR8rIWjbZGo3tk0GokfjnWfp2R) динозавры?

## Writeup

This task is pretty obvious, after opening this text file we see a morse code in there. There is no way to use online translator to translate this so I am going to write a python code.

```python
CODE = {'.-': 'A', '-...': 'B', '-.-.': 'C',
            '-..': 'D', '.': 'E', '..-.': 'F',
            '--.': 'G', '....': 'H', '..': 'I',
            '.---': 'J', '-.-': 'K', '.-..': 'L',
            '--': 'M', '-.': 'N', '---': 'O',
            '.--.': 'P', '--.-': 'Q', '.-.': 'R',
            '...': 'S', '-': 'T', '..-': 'U',
            '...-': 'V', '.--': 'W', '-..-': 'X',
            '-.--': 'Y', '--..': 'Z',

            '-----': '0','.----': '1', '..---': '2',
            '...--': '3', '....-': '4', '.....': '5',
            '-....': '6', '--...': '7', '---..': '8',
            '----.': '9'
    }
out = open('/Users/Meatball/Downloads/dino_image.png', 'wb')
with open("/Users/Meatball/Downloads/dino_code.txt") as f:
    text = f.read().split()
    decoded = ''
    for i in text:
        decoded += CODE[i]
    result = bytearray.fromhex(decoded)
    out.write(result)
out.close()
```

First of all I just translated all morse code into letters and numbers and got hex-encoded data. After that I decoded it to bytes and I saw that the first four bytes were PNG signature so I provide the last version of my python code to prevent from posting it many times. And after this we got this picture.

![dino](/FHQ/images/steganography/dino_image.png)

Flag: `what_is_gym`

### Link

https://freehackquest.com/?quest=33
