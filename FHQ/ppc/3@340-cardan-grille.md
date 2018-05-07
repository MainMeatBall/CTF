# Cardan grille #212
**Description:**

***ENG***
> Flag was consequently encrypted using **Cardan grille** 100 times. Each line in [keys](/FHQ/files/ppc/keys.txt) is a grille. The encrypted message is:

`Oaussr!dev akdby{_sfegutfnmceofs1iwnmI_0skmtw_fd}jasoeijnl_,ftme`

The example of ecrypting is [here](/FHQ/files/ppc/sample.pdf).

---

***RU***
> Флаг последовательно зашифрован с помошью **решетки Кардано** 100 раз. Каждая строка в [keys](/FHQ/files/ppc/keys.txt) - это решетка. Получившийся шифр:

`Oaussr!dev akdby{_sfegutfnmceofs1iwnmI_0skmtw_fd}jasoeijnl_,ftme`

Пример шифрования [тут](/FHQ/files/ppc/sample.pdf).

## Writeup

It is simple enough to reverse the whole thing. We do this algorithm, provided in `sample.pdf` in reverse order.

```python
def rotateinv90(matrix):
    a = list(zip(*matrix[::-1]))
    b = list(zip(*a[::-1]))
    c = list(zip(*b[::-1]))
    return c

f = open('/Users/Meatball/FHQ/keys.txt', 'r')
keys = f.read().split('\n')[::-1]
s = 'Oaussr!dev akdby{_sfegutfnmceofs1iwnmI_0skmtw_fd}jasoeijnl_,ftme'
for hex_str in keys:
    m = [[0]*8,[0]*8,[0]*8,[0]*8,[0]*8,[0]*8,[0]*8,[0]*8]
    letm = [[0]*8,[0]*8,[0]*8,[0]*8,[0]*8,[0]*8,[0]*8,[0]*8]
    for i, (op, code) in enumerate(zip(hex_str[0::2], hex_str[1::2])):
        temp = '{0:08b}'.format(int(op + code, 16))
        for a,b in enumerate(temp):
            m[i][a] = int(b)
    for i in range(8):
        for j in range(8):
            letm[i][j] = ord(s[i*8 + j])
    flag = ''
    for _ in range(4):
        m = rotateinv90(m)
        for i in range(7,-1,-1):
            for j in range(7, -1, -1):
                if m[i][j] == 1:
                    flag = chr(letm[i][j]) + flag
print(flag)
```

Flag: `ugractf{1ts_muffIn_time,s0mebody_sOlve_me!}`

### Link

https://freehackquest.com/?quest=212
