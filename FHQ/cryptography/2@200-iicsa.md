# iicsa #215
**Description:**

***ENG***
> There is a strange sequence of characters. Decode it.

`053 053 121 101 097 114 115 111 108 100 097 110 099 105 101 110 116 097 109 101 114 105 099 097 110 099 111 100 101`

---

***RU***
> Представлена странная последовательность символов. Расшифруйте её.

`053 053 121 101 097 114 115 111 108 100 097 110 099 105 101 110 116 097 109 101 114 105 099 097 110 099 111 100 101`

## Writeup

The name of the task says it pretty clear, that is just sequence of ascii codes. Let's decrypt it and submit the flag.

```python
s = '053 053 121 101 097 114 115 111 108 100 097 110 099 105 101 110 116 097 109 101 114 105 099 097 110 099 111 100 101'
flag = "".join(chr(int(i)) for i in s.split())
```

Flag: `55yearsoldancientamericancode`

### Link

https://freehackquest.com/?quest=215
