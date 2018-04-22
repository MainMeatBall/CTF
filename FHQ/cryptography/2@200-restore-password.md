# Restore password #61
**Description:**

***ENG***
> I don't remember my password, but I have this... Help me please to restore the password. `P8CnrPCH9UmsKyZrr5S4sQ==`

---

***RU***
> Я не помню свой пароль, но у меня есть это... Помоги мне пожалуйста восстановить мой пароль. `P8CnrPCH9UmsKyZrr5S4sQ==`

## Writeup

We see that this is definitely base64-encoded message, so let's decode it. We will get unreadable bytes so the only way to work with them is hex representation of them. It would be `3fc0a7acf087f549ac2b266baf94b8b1` and if you are attentive enough, you will notice that there are 32 symbols in this hash. 32 symbols almost always mean that this is md5. Let's try to decode iy and see if online bases have the original password. I will use [this one](https://md5online.org/). And it says 

```
Found : qwerty123 
(hash = 3fc0a7acf087f549ac2b266baf94b8b1)
```

Flag: `qwerty123`

### Link

https://freehackquest.com/?quest=61
