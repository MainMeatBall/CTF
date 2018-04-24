# Bitwise #178
**Description:**

***ENG***
> The flag is the input, using which the program prints 'Success!'.

---

***RU***
> Флагом являются входные данные, при которых программа печатает 'Success!'.

```python
#!/usr/bin/env python

user_submitted = input("Enter Password: ")
if len(user_submitted) != 10:
    print("Wrong")
    exit()
verify_arr = [193, 35, 9, 33, 1, 9, 3, 33, 9, 225]
user_arr = []

for char in user_submitted:
    user_arr.append((((ord(char) << 5) | (ord(char) >> 3)) ^ 111) & 255)

if (user_arr == verify_arr):
    print("Success")
else:
    print("Wrong")
```

## Writeup

From this script we can see that we need to create the array that after `((((ord(char) << 5) | (ord(char) >> 3)) ^ 111) & 255)` to every element will become the `verify_array`. The simplest way I could invent is this.

```python
import string

verify_arr = [193, 35, 9, 33, 1, 9, 3, 33, 9, 225]

flag = ''
for i in verify_arr:
	for char in string.printable:
		if ((((ord(char) << 5) | (ord(char) >> 3)) ^ 111) & 255) == i:
			flag += char
```

Flag: `ub3rs3cr3t`

### Link

https://freehackquest.com/?quest=178
