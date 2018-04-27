# Sum it numbers #211
**Description:**

***ENG***
> There are 1000 lines in the [file](/FHQ/files/ppc/num.txt) and there are 36 numbers in every line. You need to sum numbers in every column so you will have 36 sums. Take them mod 256 and take the relevant ascii-symbol, using this code. Concatenate all symbols and you will have the flag.

---

***RU***
> В [файле](/FHQ/files/ppc/num.txt) 1000 строк и в каждой строке 36 чисел. Нужно сложить все числа в пределах столбцов. Получившиеся 36 сумм необходимо поделить по модулю 256 и взять соответствующий символ в ascii таблице. Конкатeнация символов и будет флагом.

## Writeup

```python
res = [0]*36
with open('/Users/Meatball/FHQ/num.txt') as f:
    a = f.read().split()
    for i,num in enumerate(a):
    	res[i % 36] = (res[i % 36] + int(float(num))) % 256
print("".join(chr(i) for i in res))
```

Flag: `ugractf{iI's_s00_eASy_manN!Cookie#^}`

### Link

https://freehackquest.com/?quest=211
