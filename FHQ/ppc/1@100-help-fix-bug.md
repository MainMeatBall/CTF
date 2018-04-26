# Help fix bug #210
**Description:**

***ENG***
> Damn!! I wrote a program, but it doesn't work :( HELP!!!

---

***RU***
> Черт!! Написал программу, а она не работает :( ХЭЛП!!!

```python
text = '~qFmobwfpfhe`pin5unugkaqfyGhfcYf|chtugenbrtchtwl'


def mix(text):
    string = text[::2]
    string = "".join(chr(ord(string[x])-1)
                     for x in range(len(string))
                     if x%2 == 0 else chr(ord(string[x])-2))
    flag = string[::-1]
    return(flag)
    

print(mix(text))
```

## Writeup

It is a typical mistake in python's list comprehensions. The ternary statement should prevent the list comprehension for loop, so if we just swap them everythong should be fine.

```python
text = '~qFmobwfpfhe`pin5unugkaqfyGhfcYf|chtugenbrtchtwl'

def mix(text):
    string = text[::2]
    string = "".join(chr(ord(string[x])-1)
    				 if x%2 == 0 else chr(ord(string[x])-2)
                     for x in range(len(string)))
    flag = string[::-1]
    return(flag)

print(mix(text))
```

Flag: `ugractf{WeEe_fl4g_founD}`

### Link

https://freehackquest.com/?quest=210
