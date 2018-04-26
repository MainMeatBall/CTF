# Sorting #96
**Description:**

***ENG***
> Perform counting the number of [values](https://drive.google.com/open?id=1xYeUeTHEa4sB8UChRz9NXAtmknTLH_ms) in different ranges and record the results on a single line separated by spaces.

For example: `1000 2000 3000 4000 5000 6000`

---

***RU***
> Выполните подсчет количества [значений](https://drive.google.com/open?id=1xYeUeTHEa4sB8UChRz9NXAtmknTLH_ms) по разным диапазонам и результаты запишите в одну строку через пробелы.

Например: `1000 2000 3000 4000 5000 6000`

```
Range1: 100 < x < 150 
Range2: x > 2000 
Range3: 120 < x < 500 
Range4: -1000 < x < -120 
Range5: -5000 < x < -3000 
Range6: -10 < x < 10
```


## Writeup

```python
i = [0,0,0,0,0,0]
with open('/Users/Meatball/Downloads/data') as f:
    x = f.read().split()
    for a in x:
         if int(float(a)) > 100 and int(float(a)) < 150:
             i[0] += 1
         if int(float(a)) > 2000:
             i[1] += 1
         if int(float(a)) > 120 and int(float(a)) < 500:
             i[2] += 1
         if -1000 < int(float(a)) and int(float(a)) < -120:
             i[3] += 1
         if int(float(a)) > -5000 and int(float(a)) < -3000:
             i[4] += 1
         if int(float(a)) > -10 and int(float(a)) < 10:
             i[5] += 1
print(" ".join(map(str,i)))
```

Flag: `24561 3999977 189313 439061 999842 9473`

### Link

https://freehackquest.com/?quest=96
