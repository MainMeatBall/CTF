# Permutation #197
**Description:**

***ENG***
> Let's permute something! 

`etuavf{grcmyedsi'ryasihfhnguflhnulugsffi gfi } fln`

---

***RU***
> Давайте что-нибудь попереставляем! 

`etuavf{grcmyedsi'ryasihfhnguflhnulugsffi gfi } fln`

## Writeup

The name of the task says that this is the permutation cipher. The task from ugractf so we definitely know the first symbols of the flag are `ugractf{...` so let's try to permute this broken flag to its original state. I will use python for this purpose. Accidently you will see that the letter `r` and `c` have index 8 and 9, so probably the permutation block would be 10 letters long. There are only to ways to allocate last two letters and only one way will create the recognizeable message inside the curly braces.

```python
s = 'etuavf{grcmyedsi\'ryasihfhnguflhnulugsffi gfi } fln'
flag = "".join((i[2]+i[7]+i[8]+i[3]+i[9]+i[1]+i[5]+i[6]+i[0]+i[4]) for i in [s[i:i+10] for i in range(0, len(s), 10)])
```


Flag: `ugractf{everydayi'mshufflingshufflingshuffling}`

### Link

https://freehackquest.com/?quest=197
