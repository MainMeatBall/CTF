# Mariarti #56
**Description:**

***ENG***
> Mariarti wants to say something;)

---

***RU***
> Мариарти хочет что-то сообщить;)


`NOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOBS NOOBS NOOOOOOOOOOOOOOOOOOOBS >_< NOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOOBS >_< NOOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOOOBS >_< NOOOOOOOOOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOBS NOOOOBS`

## Writeup

This task requires some imagination. Actually, it is pretty simple. Every `NOOBS` word has not less then 2 letters `O` in it and less then 27. So it is reasonable to suppose that it is just an alphabet substitution. So I will write a python code to reveal the message.

```python
import string
s = 'NOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOBS NOOBS NOOOOOOOOOOOOOOOOOOOBS >_< NOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOOBS >_< NOOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOOOBS >_< NOOOOOOOOOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOBS NOOOOOOOOOOOOOOOOOOBS NOOOOBS'
alphabet = '_' + string.ascii_lowercase
flag = "".join(alphabet[i.count('O')] for i in s.split(' '))
```

Flag: `noobs_is_just_word`

### Link

https://freehackquest.com/?quest=56
